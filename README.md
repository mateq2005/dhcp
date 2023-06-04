# DHCP

### Install DHCP Server

```
apt-get install isc-dhcp-server -y
```

```
systemctl start isc-dhcp-server
systemctl enable isc-dhcp-server
```

### Configure DHCP Service

```
nano /etc/default/isc-dhcp-server
```

```
INTERFACESv4="eth0"
```

```
nano /etc/dhcp/dhcpd.conf
```