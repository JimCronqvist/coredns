# CoreDNS - Docker

CoreDNS is a modern lightweight DNS Server written in Go.

A starter setup using the official CoreDNS Dockerfile that contains the most common things required. 

- Hosts file format
- DNS Zone file format (RFC 1035-style master file)
- Rewrite examples included 
- Automatically checks for changes every 10 seconds, except for zone files which is checked every 60 seconds.

## Quick Start
Start the CoreDNS service using: 

```docker-compose up -d```

This will bind it to localhost:53 by default.

## Further reading
[CoreDNS](https://coredns.io)
