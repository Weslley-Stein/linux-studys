#DDNS
- ddns-confgen -k <key> > dhcp.key
- mv db.forward /var/lib/bind/db.forward
- mv db.reverse /var/lib/bind/db.revers
- vim /etc/bind/named.conf.local
	> zone "domain" {
	> 	type master;
	>	file "/var/lib/bind/your_zone";
	>	update-policy {
	>		grant <key> wildcard *.<your_domain> A DHCID;
	>	};
	>};
	>zone "reverse_domain" {
	>	type master;
	>	file "/var/lib/reverse_zone";
	>	update-policy {
	>		grant <key> wildcard *.<your_domain> PTR;
	>	};
	>};
- cp /etc/bind/dhcp.key /etc/dhcp/
- vim /etc/dhcp/dhcpd.conf
	> include "/path/of/your/key/file.key";
	> option domain-name "your_domain";
	> option domain-name-servers "ip_or_nameserver";
	> ddns-updates on;
	> ddns-updat-style standard;
	> authoritative;
	> subnet 0.0.0.0 netmask 0.0.0.0 {
	>	range 0.0.0.0 0.0.0.0;
	>	option subnet-mask 0.0.0.0;
	>	option domain-name "example.org";
	>	option domain-name-servers <ip>;
	<	option broadcast-address <ip;
	> }
	> zone <domain>. {
	> 	primary <ip>;
	>	key file.key
	> } 

