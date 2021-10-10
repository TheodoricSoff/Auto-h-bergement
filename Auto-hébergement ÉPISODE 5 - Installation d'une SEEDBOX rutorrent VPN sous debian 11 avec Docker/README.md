`su root`

`adduser docker-compose`

`id docker-compose`

`cd /home/docker-compose`

`mkdir vpn`
`mkdir rutorrent`

`cd vpn`

`nano TUN.sh`

`Contenue du fichier TUN.sh`

`chmod 0755 TUN.sh`

`./TUN.sh`

`mkdir config`

`cd config`

`pwd`

`cd ..`

`nano docker-compose.yml`

Contenue du fichier VPN-docker-compose.yml

`nano docker-compose.yml`

`cd ..`

`cd rutorrent`

`mkdir config`

`cd config`

`pwd`

`cd /data/data`

`pwd`

`cd /home/docker-compose/rutorrent`

`nano docker-compose.yml`

`RUTORRENT-docker-compose.yml`

`docker network create vpn-network`

`cd ..`

`cd vpn`

`docker-compose up -d`

`cd ..`

`cd rutorrent`

`docker-compose up -d`

`docker exec -it rutorrent gen-http-passwd`



`adduser docker-compose data`

`sudo chown root:data /data`
`sudo chown root:data /data/data`

`chmod 775 /data`
`chmod 775 /data/data`
