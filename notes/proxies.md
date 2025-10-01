---
created: 2024-04-22T11:41
updated: 2024-12-09T14:29
---
#networking #system-design 


## forward proxy 
sits between client and internet
- bypass browsing restrictions
- mask ip
### usage examples
shoe botting to mask ip of clients
used by schools or businesses to block certain sites

## reverse proxy
sits between internet and server(s)
- protects the website ip (inversly)
- can be used to [[load balancer]], distributing traffic
- can cache static content
- handle ssl encryption
### usage examples
most websites typically utilize many reverse proxy
- cloudflare layer
- [[load balancer]] layer
