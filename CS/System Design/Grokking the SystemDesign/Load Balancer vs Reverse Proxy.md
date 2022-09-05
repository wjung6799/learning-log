Loadbalancing is needed for multiple servers but reverse proxy can used for even one because main purpose of reverse proxy is to provide security whereas loadbalancers are there to provide well load balancing.

Load balancer provies session persistence.

Reverse proxy provides

- Increased security
- Increased scalability and felxibility.
- Web acceleration
- Compression (Compressing server responses before returning them)
- SSL termination: Decrpytion and ecrpytion can be expensive. By doing that between servers, backend server can focus on serving the data without having to encrpyt and decrypt
- Caching
