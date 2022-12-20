# Quick install


(Supports multiple Odoo instances on one server)

Install [docker](https://docs.docker.com/get-docker/) and [docker-compose](https://docs.docker.com/compose/install/) yourself, then run:
``` bash
sudo apt update && apt upgrade
sudo apt install docker docker-compose -y
```
Then
``` bash
git clone https://github.com/thaichikma/npm.git npm
```

and

``` bash
docker-compose up -d
```

to set up Nginx proxy manager instance @ `localhost:81` (default user/ password: `Email:    admin@example.com`/ `Password: changeme` )


# Usage

Start the container:
``` sh
docker-compose up -d
```

**Run NPM**:

``` bash
docker-compose up -d
```

**Restart NPM**:

``` bash
docker-compose restart
```

**Stop NPM**:

``` bash
docker-compose down
```
**Upgrading NPM**:
``` bash
docker-compose pull
docker-compose up -d
```
**Crontab**:
At 00:00 every day restart docker container npm
``` bash
0 0 * * * docker-compose -f /www/ilanni.com/docker-compose.yml start > /dev/null
```
**Docker commit**:

``` bash
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

More info: https://docs.docker.com/engine/reference/commandline/inspect/
# Examples:
$ **docker ps**

``` bash
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS              NAMES
c3f279d17e0a        ubuntu:12.04        /bin/bash           7 days ago          Up 25 hours                            desperate_dubinsky
197387f1b436        ubuntu:12.04        /bin/bash           7 days ago          Up 25 hours                            focused_hamilton
```
**docker commit c3f279d17e0a  svendowideit/testimage:version3**
``` bas
f5283438590d
```
$ **docker images**

``` bas
REPOSITORY                        TAG                 ID                  CREATED             SIZE
svendowideit/testimage            version3            f5283438590d        16 seconds ago      335.7 MB
```

# **Docker Portainer**
* Install
``` bas
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
# docker-compose.yml

* jc21/mariadb-aria:latest
* jc21/nginx-proxy-manager:latest

