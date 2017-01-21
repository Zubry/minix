# SSHing into Minix

To get the IP for SSH, run the following command in Minix through the VM:

```shell
$ ifconfig
> /dev/ip: address 172.16.107.128 netmask 255.255.255.0 mtu 1500
```

You can now SSH into Minix from your terminal by running

```shell
$ ssh root@172.16.107.128 -p 22
```

# Syncing content **to** Minix

From your native terminal, run rsync

```shell
$ rsync -auPv ./ root@172.16.107.128:/usr/src
```

This will push updates to the VM with the following options:

**-u**: only pushes recently updated files

**-a**: recursively pushes all files

**-P**: prints the progress of the transfer

**-v**: verbose
