## 👋 Welcome to i2p.md 🚀  

i2p i2p  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update i2p.md
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/i2p.md/dataDir"
git clone "https://github.com/dockermgr/i2p.md" "$HOME/.local/share/CasjaysDev/dockermgr/i2p.md"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/i2p.md/dataDir/." "$HOME/.local/share/srv/docker/i2p.md/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/i2p.md:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-i2p.md \
--hostname casjaysdev-i2p.md \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/i2p.md/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/i2p.md/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/i2p.md:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  i2p.md:
    image: casjaysdevdocker/i2p.md
    container_name: i2p.md
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-i2p.md
    volumes:
      - $HOME/.local/share/srv/docker/i2p.md/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/i2p.md/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
