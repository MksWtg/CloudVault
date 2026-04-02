
```csharp
// the interface that suborchs need to inject for implementation- does this talk to the agent?
public interface ISubOrchestratorCommonComponentVersionCache
{
    bool TryGetHostVersions(string hostFqdn, out IEnumerable<Version> hostVersions); //gets all versions on a single host
    bool TryGetHostsWithVersion(Version targetVersion, out IEnumerable<CargoWiseHost> hosts); //Gets all hosts with verison x
}

// This is the common component in the case that we have in-memory caching with dictionary.
public class SubOrchestratorCommonComponent
    : OrchestratorCommonService.OrchestratorCommonServiceBase, ISubOrchestratorCommonComponentVersionCache
{
 private readonly Dictionary<CargoWiseHost, HashSet<Version>> cargoWiseHostInstalledVersions;
 
 public SubOrchestratorCommonComponent()
 {
  this.cargoWiseHostInstalledVersions = new Dictionary<CargoWiseHost, HashSet<Version>>();
 }
 
    public override async Task<Empty> RegisterAgent(
        RegisterAgentRequest request, ServerCallContext context)
    {
  var certificate = context.AuthContext?.FindClaimValue("x509_cert");
  if (certificate == null) 
  {
   throw new RpcException(new Status(StatusCode.Internal, "Error processing client certificate"));
  }
  var certificateFingerprint = request.certificateFingerprint;
  var expectedCertificateFingerprint = GetCertificateFingerprint(cert);

  if (!certificateFingerprint.Equals(expectedCertificateFingerprint, StringComparison.OrginalIgnoreCase))
  {
   throw new RpcException(new Status(StatusCode.PermissionDenied, "Client certificate fingerprint does not match expected fingerprint"));
  }

  var cargoWiseHost = new CargoWiseHost
  {
   FullyQualifiedDomainName = request.fqdn,
   DomainName = request.domainName,
   HostName = request.hostName,
   DataCentre = request.dataCentre,
   LastHeartBeat = DateTime.NowUtc,
  };
        this.cargoWiseHostInstalledVersions[host] = new HashSet<Version>();

        return new Empty();
    }

    public override async Task<Empty> ReportInstalledVersions(
        ReportInstalledVersionsRequest request, ServerCallContext context)
    {
  // check if the host is registered as a known host first
        var registeredHost = this.cargoWiseHostInstalledVersions.Keys.FirstOrDefault(host => host.FullyQualifiedDomainName.Equals(request.fqdn, StringComparison.OrdinalIgnoreCase);
  if (registeredHost == null) 
  {
   throw new RpcException(new Status(StatusCode.NotFound, "Unregistered Host"));
  }
  
        this.cargoWiseHostInstalledVersions[registeredHost].AddRange(request.installedVersions);
            
  return new Empty();
    }

    public bool TryGetHostVersions(string hostFqdn, out IEnumerable<Version> hostVersions)
    {
        var registeredHost = this.cargoWiseHostInstalledVersions.Select(host => host.FullyQualifiedDomainName.Equals(hostFqdn, StringComparison.OrdinalIgnoreCase));
        if (registeredHost == null)
        {
            return false;
        }
        
        if (!this.cargoWiseHostInstalledVersions.ContainsKey(registeredHost))
        {
            return false;
        }

        hostVersions = this.cargoWiseHostInstalledVersions[registeredHost];
        return true;
    }

    public bool TryGetHostsWithVersion(Version targetVersion, out IEnumerable<CargoWiseHost> hosts)
    {
        hosts = new HashSet<CargoWiseHost>();
        foreach (var host in this.cargoWiseHostInstalledVersions.Keys)
        {
            if (this.cargoWiseHostInstalledVersions[host].Contains(targetVersion))
            {
               hosts.Add(host);
            }
        }
        return hosts.Length > 0;
    } 
 
 static string GetCertificateFingerprint(string certificateData)
 {
  using (var sha256 = SHA256.Create()) 
  {
   byte[] certBytes = Convert.FromBase64String(certificateData);
   byte[] hash = sha256.ComputeHash(certBytes);
   return BitConverter.ToString(hash).Replace("-", ":");
  }
 }
}
// -------------

// now use in suborchestrator proj, lets use PCO for example
public class Program
{
    //...
    var webAppBuilder = WebApplication.CreateBuilder();

    //... composition root stuff

    webAppBuilder.Services.AddGrpc();
 var webApp = webAppBuilder.ConfigureBuilder().Build();

    webApp.MapGrpcService<SubOrchestratorCommonComponent>();
    //...
}

// -------------

// now to access the cache, inject IServiceProvider and grab the service from there... 
public class HostRouter(ISubOrchestratorCommonCache cache) {
    public void RouteHost(string targetVersion)
    {
        //...
        if (TryGetHostsWithVersion(targetVersion, our var hostsWithVersion))
        {
           DoRouting();
        }
        else
        {
           DoSomeOtherStuff();
        } 
        //...
    }
}
```