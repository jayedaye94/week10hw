### QA Individual Work

## DNS and SSL/TLS
- Explain what the traceroute and dig commands do. Compare and contrast.
    - Traceroutes is used in command lines to trace the routes used for specific data. Can help identify potential issues with the route being used along with pings to each router on the way. Dig commands queries DNS servers to make sure the domain resolves any issues correctly. 
    - To compare and contrast, traceroutes follows the routes used to reach it's destination and can diagnose a potential bad route being used. While dig is mainly used for DNS, it troubleshoots any DNS issues.

- What are the 3 or 4 most common DNS records and what are their use cases?
    - A record which resolves domain names to an IPv4 address
    - AAAA record resolves domain names to an IPv6 address.
    - CNAME record resolves a domain name to another domain name.
    - MX record, which points to a server where emails are delivered for that email.

- Give an overview of the steps in a TLS handshake.
    - When the client is requesting connection to servers using SSL, they also request for the server to authenticate.
    - The server sends a cert that authenticates itself. 
    - Once authenticated, it makes a virtual agreement between the two.
    - Now they'll both send encrypted data back and forth.


- How does an SSL/TLS cert know what domain it belongs to?
    - A request is submitted to the Cert Authority, and it must include the domains in the the request.

- What is a certificate authority?
    - It issues Certs. Digital certs.

## Load Balancers

- How do application load balancers in GCP offload (decrypt) SSL? 
    - The offloading of the SSL, happens when the load balancer is the one that decrypts incoming HTTPS traffic, no the backend servers. The clients encrypted connection ends at the load balancer, then communicates with the backends in a separate connection.


- Are there use cases to have in flight encryption from the backend service to the backend itself? 
    - Certain use case for a flight encryption, would probably be any establishment that has to follow HIPAA like a hospital or medical facility. They would need to keep data encrypted in the backend systems to follow HIPAA regulations and keep data from being breached and the backends have to communicate with each other.

## Cloud Domain/DNS
- Can multiple domains end up pointing to the same LB? 
    - Yes, mainly for multi-tenant apps to point to the same LB. 


- In the context of Cloud DNS, what are zones?
    - In cloud DNS, zones come in both private & public. Public zones are open to the public internet, which can be websites, API, LB's, etc. Private DNS zones can't be accessed through public channels. Only inside your private VPC for internal services for either yourself or private enterprises.
