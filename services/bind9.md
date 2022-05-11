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
