
Prerequisites: [[What is RDP]]

RD Gateway is a microsoft technology. It is just a microsoft server, typically internet facing, with some extra software enabled: `Install-WindowsFeature RDS-Gateway`. this is called a role. Other roles are IIS Server, RD Session Host (to become a terminal server), DNS Server. RD Gateway includes adding an endpoint `/rpc/rpcproxy.dll` to IIS that accepts RDP over HTTPS.

It wraps RDP traffic inside HTTPS so you can reach a terminal server over the internet without opening RDP's native port in the firewall. From the network it looks like web traffic.

RD Gateway Service (TSGateway) is the windows service that does teh actual unwrapping and forwarding. IIS hands the connection off to this service which strips the HTTPS wrapper and proxies the RDP traffic through to the terminal server.

Your PC sends and receives data over 443. It is connected to an RD gateway which is a machine that is internet facing that has been configured to accept an HTTPS connection, and unwraps the 443 data, turns it into 3389 remote desktop data and sends it to the terminal server like a reverse proxy (nginx, HAProxy).

