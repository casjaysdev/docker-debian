## 👋 Welcome to debian 🚀  

debian README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update debian
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/debian/rootfs"
git clone "https://github.com/dockermgr/debian" "$HOME/.local/share/CasjaysDev/dockermgr/debian"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/debian/rootfs/." "$HOME/.local/share/srv/docker/debian/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-debian \
--hostname debian \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-debian/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-debian/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/debian:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/debian
    container_name: casjaysdevdocker-debian
    environment:
      - TZ=America/New_York
      - HOSTNAME=debian
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-debian/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-debian/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/debian
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/debian" "$HOME/Projects/github/casjaysdevdocker/debian"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/debian"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
