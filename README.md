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

```
authoritative;

default-lease-time 660;
max-lease-time 6300;

# range of subnet
range 192.168.0.2 192.168.0.20;

# gateway address
option routers 192.168.0.1;

# DNS server address
option domain-name-servers 8.8.8.8, 8.8.4.4;
}
```

### Configure DHCP Server to Assign Static IP to Client

```
nano /etc/dhcp/dhcpd.conf
```

```
host client1 {

hardware ethernet 4c:bb:58:9c:f5:55;

fixed-address 192.168.0.5;

}
```