# CoreDNS - Docker

CoreDNS is a modern lightweight DNS Server written in Go.

A starter setup using the official CoreDNS Dockerfile that contains the most common things required. 

- Hosts file format
- DNS Zone file format (RFC 1035-style master file)
- Rewrite examples included 
- Automatically checks for changes every 10 seconds, except for zone files which is checked every 60 seconds.

## Quick Start
Start the CoreDNS service using: 

```
docker-compose up -d
```

This will bind it to localhost:53 by default. 

## Troubleshooting

- *ERROR: for coredns  Cannot start service coredns: driver failed programming external connectivity on endpoint coredns (...): Error starting userland proxy: listen tcp4 0.0.0.0:53: bind: address already in use*

If you are using Docker on a Linux OS which has systemd-resolved enabled by default (ex. Ubuntu), you will notice that 
port 53 is already occupied. 

"Disable" systemd-resolved in this case by running the following command:

```
echo 'DNSStubListener=no' | sudo tee -a /etc/systemd/resolved.conf
sudo rm -f /etc/resolv.conf
sudo ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf
sudo systemctl restart systemd-resolved
```

## Further reading
[CoreDNS](https://coredns.io)
