---
title: "SSH"
date: 2023-01-31T23:10:43+01:00
draft: false
---

## Reset known host for hostname
```fish
ssh-keygen -R $hostname
```

## Create generic SSH key
```fish
ssh-keygen -a 1000 -t ed25519 -f $outfile -C "host-user->target"
```
