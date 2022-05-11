# Nginx Basic Setup

### Config Files
- /etc/nginx/nginx.conf: general configurations
- /etc/nginx/sites-available/: Here you can put configurations for your website, such as
	```sh
		server {
			listen <port>;#Port with nginx will listen
			root <absolute_path>;#Location of your website
			index index.html;#Name of your index
			server_name <DNS_zone>;#Your Dns Zone
		}
	```
- /etc/nginx/sites-enabled/: symbolic links for your availables sites

### Commands
- systemctl start nginx: start nginx
- systemctl enable nginx: enable nginx to start on boot
- nginx -t: check if your configurations files are ok
