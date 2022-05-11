# Bind9

### Defitions
- DNS: Domain Name System basically its a way to label an IP with a Name.
- Zone: A Zone its a "pool" of (hostname,ip) pairs. with have a root domain, like .com
	- Foward: A zone who wait for an Hostname return you his IP
	- Reverse: A zone who wait for an IP and return you his hostname
- Registry:
	- types: 
		- NS: domain=nameserver
		- A: hostname=ip
		- AAAA: hostname=ipv6
		- CNAME: subdomain=domain
		
### Configuration Files:
- /etc/bind/named.conf.local : 
	here you declare your zones, like that
	```sh
		zone "domain" {
			type master;
			file "absolute_path";
		};
		
		zone "reverse_ip.in-addr.arpa" {
			type master;
			file "absolute_path";
		};
	```
- /etc/bind/namef.conf.options :
- /etc/bind/db.<something> :

### DDNS
- ddns-confgen -k <key> > dhcp.key
- vim /etc/bind/named.conf.local
	> zone "domain" {
	> 	type master;
	>	file "/etc/bind/your_zone";
	>	update-policy {
	>		grant <key> wildcard *.<your_domain> A DHCID;
	>	};
	>};
	>zone "reverse_domain" {
	>	type master;
	>	file "/etc/bind/reverse_zone";
	>	update-policy {
	>		grant <key> wildcard *.<your_domain> PTR;
	>	};
	>};
- cp /etc/bind/dhcp.key /etc/dhcp/
- vim /etc/dhcp/dhcpd.conf
	> option domain-name "your_domain";
	> option domain-name-servers "ip_or_nameserver";
	> ddns_updates on;
	> ddns_update_style standard;
	> authoritative;
	> subnet 0.0.0.0 netmask 0.0.0.0 {
	>	range 0.0.0.0 0.0.0.0;
	>	option subnet-mask 0.0.0.0;
	>	option '

