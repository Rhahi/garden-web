---
title: "Wireguard"
date: 2023-01-31T23:10:43+01:00
draft: false
---

https://wiki.archlinux.org/title/WireGuard

## Host
```ini
[Interface]
Address = 10.0.0.1/32
ListenPort = 51821
PrivateKey = # wg genkey > host.key

[Peer]
PublicKey = # client's pubkey
PresharedKey = # wg genpsk > host-client.psk
AllowedIPs = 10.0.0.2/32
```

## Client
```ini
[Interface]
PrivateKey = # wg genkey > client.key
Address = 10.0.0.2/24 # not sure if this should match host's peer setting
#DNS = 1.1.1.1, 1.0.0.1

[Peer]
PublicKey = # host's pubkey
PresharedKey = # wg genpsk > host-client.psk
AllowedIPs = 0.0.0.0/0, ::/0 # tunnel all connections
Endpoint = #ip/url:port
```
