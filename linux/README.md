# Start

```bash
    # find result with date
    find [search-path] -name [search-file-name] -printf [format]
    find /data -name jupyterhub_config.py -printf "%p %TY-%Tm-%Td %TH:%TM:%TS %Tz\n"
```

## Set IP

Create ifconfig file for ethernet id as ifcfg-enp0s8 in /etc/sysconfig/network-scripts/ and give it the following contents:

``` bash
DEVICE=enp0s8
BOOTPROTO=static
ONBOOT=yes
IPADDR=192.168.50.101
NETMASK=255.255.255.0
```

## Change hostname

```bash
    hostnamectl set-hostname [new-host-name]
```
