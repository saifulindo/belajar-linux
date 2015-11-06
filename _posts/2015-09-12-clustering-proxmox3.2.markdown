---
layout: post
title: "Clustering 2 Node with ProxmoxVE-v3.4"
date: 2015-09-10
categories:
---

## Documentation
#### Mengganti Hostname

Buka file `hostanme` di `/etc/hostname` ganti nama hostname-nya misalnya, yang tadinya `pve` diganti dengan `nodecomp1`.
```
# nano /etc/hostname
```
Kemudian buka file `hosts` di `/etc/hosts`:
```
nano /etc/hosts
```
Rubah seperti berikut,
```
127.0.0.1 localhost.localdomain localhost
192.168.100.11 pve.serveroke.com pve pvelocalhost
```
Ganti menjadi,
```
127.0.0.1 localhost.localdomain localhost
192.168.100.11 nodecomp1.serveroke.com nodecomp1 pvelocalhost
```
Kemudian lakukan penggandaan file atau mengganti nama file pve-lama ke pve-baru:
```
# cd /etc/pve/nodes/
# mv pve-lama pve-baru
# reboot
```

#### Insert antar hostname:
Lakukan insert antar hostname, ini dilakuan opsional karena bisa menggunakan ip untuk clustering-nya. akan tetapi ini dilakukan untuk memudahkan konfigurasi, jadi yang dihafal adalah hostname-nya bukan ip address, yah... bisa dibilang untuk mengurangi stress.
```
# nano /etc/hosts
```
Edit seperti berikut,
```
127.0.0.1 localhost.localdomain localhost
192.168.100.11 nodecomp1.serveroke.com nodecomp1 pvelocalhost
# Tambahannya
192.168.100.21 nodecomp2.serveroke.com nodecomp2
```
Begitupula, sebaliknya dilakukan di node yang lain.
Berikutnya adalah ping antar hostname:
```
# ping <hostname>
```
#### Clustering
Yang pertama adalah membuat sebuah ID cluster, dengan menentukan salah satu node sebagai master dan node yang lain adalah slave,
```
pvecm create nodecomp1cluster [master]
pvecm add nodecomp2 [Slave]
```
Setelah itu anda akan diminta untuk memasukkan passwordnya `nodecomp2`, maka yang terjadi kedua node akan saling terbaca satu sama lain.

Selanjutnya mungkin kearah konfigurasi melalui WebGUI.

#### Source
1. [http://tutorial4itindonesia.blogspot.co.id/2015/01/membuat-cluster-pada-proxmox-32-4.html] http://tutorial4itindonesia.blogspot.co.id/2015/01/membuat-cluster-pada-proxmox-32-4.html
2. [https://www.youtube.com/watch?v=tTy9axM1jT0] https://www.youtube.com/watch?v=tTy9axM1jT0
