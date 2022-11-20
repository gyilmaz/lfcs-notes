# Useful Command

## Basic

* `/etc/hosts` : static host resolution
* `ss -tunlp` : listen ports
* `ip a` : show ip addrs of devices
* `ip a add <ip> <> <deviced>` : set new ip address
* `ip route show` : show route
* `ip route add <range> via <network device ip>` : add route
* `ip route add <range> via <network device ip> <device name> <interface> `: add route with device and interface
* `ip route del <range>` : delete route
* `ip route add default via <network ip>` : adds a gateway
* `netstat -natp` : show port listen with proccess name (tips: `-tulpn` & grep `LISTEN`)
* `hostnamectl` : check hostname system
* `nmcli`
* `nmcli connection modify eth1 +ipv4.routes "<range> <dest>"` : add network route by device (change `+` to `-` if want to remove)
* `nmcli device reapply eth1` : reapply config
* `nmcli connection show` : list all connections then take the name and add autoconnections to make it dynamic
`nmcli connection modify enp0s3 autoconnect yes`

## Start,stop and check status of network services

*`sudo ss -ltunp` : ss can be used  to check status of sshd(l listening, -t TCP connection, -u UDP connection, -n numberic values) (p processes sudo required to see process) "tunnel p"
*

## Timezone

* `timedatectl list-timezones` : list timezones
* `timedatectl set-timezone <timezone>` : set timezone
* `timedatectl set-local-rtc <1/0>` : set real-time clock

## Firewall

* `firewall-cmd --add-port=<port>/tcp --permanent` : add permanent listen rule tcp
* `firewall-cmd --add-service=<services> --permanent` : allow service
* `firewall-cmd --list-all` : list all firewall rules
* `firewall-cmd --remove-port=<port>`: remove by port
* `firewall-cmd --add-source=<ip> --zone=trusted --permanent` : add ip address range to trusted zone
* `firewall-cmd --runtime-to-permanent` : change runtime rule to permanent

## DNS

* `/etc/resolv.conf` : Add new nameserver (DNS), format: `nameserver <ip>`

## Configure networking and hostname resolution statically or dynamically (CENTOS)

* `ip link show` or `ip l` : display network adaptor and ip addresses configured
* `ip address show` or `ip a` : it displays different NATs 
* `ip route show` or `ip r` : it dispays route 
* `cat /etc/resolv.cof` : to see nameserver
* `ls /etc/sysconfig/network-scripts/` : look for network adapter BOOTPROTO variable none is static and dhcp is dynamic
