#DHCP	

### Configurations File
- /etc/dhcp/dhcpd.conf
	```sh
		option domain-name "<zone>";#Specify the zone
		option domain-name-servers <ip>;#Specify the DNS Server
		authoritative;#its say that server its the DHCP Server

		subnet <network> netmask <subnet-mask> {
			range <ip> <ip>;
			option subnet-mask <subnet_mask>;
			option broadcast-address <ip>;
			option domain-name "<zone>";
			option domain-name-server <ip>;
		}

		host <name> {
			hardware ethernet <mac_address>;
			fixed-adress <ip>;
		}
	```
- /etc/default/isc-dhcp-server:
	```sh
		interfacesv4="<interface>"# Speficy 
	```
- /var/lib/dhcp/dhcpd.leases
	
