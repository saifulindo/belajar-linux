---
layout: post
title: "Clustering 2 Node with ProxmoxVE-v3.4"
date: 2015-09-11
categories:
---

## Documentation
#### Mengganti Hostname

```
nano /etc/hostname
nano /etc/hosts
cd /etc/pve/nodes/
mv pve-lama pve-baru
reboot
```
#### insert antar hostname:

```
nano /etc/hosts
ping <hostname>
```
#### Clustering

```
pvecm create node1cluster [master]
pvecm add node-smkti1 [Slave]
```