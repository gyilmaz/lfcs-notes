# Useful Command

## Basic

* `/etc/hosts` : static host resolution
* `ss -tunlp` : listen ports
* `ip a` : show ip addrs of devices
* `ip a add <ip> <> <deviced>` : set new ip address
* `ip route show` : show route
* `ip route add <range> via <network device ip>` : add route
* `netstat -natp` : show port listen with proccess name (tips: `-tulpn` & grep `LISTEN`)
* `hostnamectl` : check hostname system
* `nmcli`
* `nmcli connection modify eth1 +ipv4.routes "<range> <dest>"` : add network route by device (change `+` to `-` if want to remove)
* `nmcli device reapply eth1` : reapply config

## Timezone

* `timedatectl list-timezones` : list timezones
* `timedatectl set-timezone <timezone>` : set timezone
* `timedatectl set-local-rtc <1/0>` : set real-time clock

## Firewall

* `firewall-cmd --add-port=<port> --permanent` : add permanent listen rule tcp
* `firewall-cmd --add-service=<services> --permanent` : allow service
* `firewall-cmd --list-all` : list all firewall rules
* `firewall-cmd --remove-port=<port>`: remove by port
* `firewall-cmd --add-source=<ip> --zone=trusted --permanent` : add ip address range to trusted zone
* `firewall-cmd --runtime-to-permanent` : change runtime rule to permanent

## DNS

* `/etc/resolv.conf` : Add new nameserver (DNS), format: `nameserver <ip>`