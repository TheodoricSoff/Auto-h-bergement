### Activer la connexion ssh en root :

`su root`

`nano /etc/ssh/sshd_config`

`"PermitRootLogin without-password" on remplace par "PermitRootLogin yes"`

`/etc/init.d/ssh restart`


 ### Installation driver realtek :

`apt install software-properties-common`

`add-apt-repository non-free`

`apt update`

`apt install firmware-misc-nonfree firmware-netxen firmware-realtek`

`apt-get install sudo`

 ### Configuration ip fixe et dns :

`ip addr`

`sudo nano /etc/network/interfaces`

`Contenue du fichier Interface`

`sudo nano /etc/resolv.conf`

`Contenue du fichier resolv.conf`

`reboot`

 ### Installation nginx :

`apt update`

`apt install nginx`

`sudo systemctl status nginx`

`sudo systemctl enable nginx`

`sudo nginx -v`

 ### Installation docker :
 ## Si erreur copié les commande depuis : https://docs.docker.com/engine/install/debian/#install-using-the-repository

`apt-get update`

`sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release`

`curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`

`echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`

`sudo apt-get update`

`sudo apt-get install docker-ce docker-ce-cli containerd.io`

`sudo docker run hello-world`

`docker ps -a`

`docker rm "container id"`

 ### Installation docker-compose :

``sudo curl -L https://github.com/docker/compose/releases/download/1.25.3/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose``

`sudo chmod +x /usr/local/bin/docker-compose`

`docker-compose --version`

`cd /home`

`mkdir test`

`cd test`

`nano docker-compose.yml`

`Contenue du fichier docker-compose.yml`

`docker-compose up`

`docker ps -a`

`docker rm "container id"`

`rm -rf /home/test`

> SOURCE : https://docs.docker.com/engine/install/debian/#install-using-the-repository
