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
--name casjaysdev-debian \
--hostname debian \
-e TZ=${TIMEZONE:-America/New_York} \
casjaysdev/debian:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/debian
    container_name: casjaysdev-debian
    environment:
      - TZ=America/New_York
      - HOSTNAME=debian
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdev/debian
```
  
OR
  
```shell
git clone "https://github.com/casjaysdev/debian" "$HOME/Projects/github/casjaysdev/debian"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdev/debian"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/casjaysdev) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  
