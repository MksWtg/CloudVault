
Prerequisites: [[What is RDP]]

RD Gateway is a microsoft technology. It is a role in windows server.

It wraps RDP traffic inside HTTPS so you can reach a terminal server over the internet without opening RDP's native port in the firewall. From the network it looks like web traffic. After the network interface 

Your PC sends and receives data over 443. It is connected to an RD gateway which is a machine that is internet facing that has been configured to accept an HTTPS connection, and unwraps the 443 data, turns it into 3389 remote desktop data and sends it to the terminal server like a reverse proxy (nginx, HAProxy).