# ad-blocking
# DNS level ad-blocking with Dokcer
# get pi.hole image for docker 
docker pull pihole/pihole
# find your local IP
cmd-> "ipconfig" 
192.168.1.1
# run docker with your IP (192.168.1.1 in my case)
docker run -d --name pihole -e ServerIP=192.168.1.1 -e WEBPASSWORD="password" -e DNS1=8.8.8.8 -p 9080:80 -p 53:53/tcp -p 53:53/udp -p 9443:443 pihole/pihole:latest
# default password will be "password", change it afterwards. Connect host OS port 9080 to pi.hole's port 80 and 9443 to pi.hole's port 443.
# DNS server is running on port 53 (you can leave it as it is)
