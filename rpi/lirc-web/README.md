# Build

```bash
docker build -t flochtililoch/rpi-lirc-web rpi/lirc-web
```

# Run

```bash
docker run -d \
           -it \
           --name lirc-web \
           --restart=always \
           --privileged \
           -p 3000:3000 \
           --device /dev/mem:/dev/mem \
           -v /lib/modules:/lib/modules \
           -v ~/docker_images/config/lirc:/etc/lirc \
           -v ~/docker_images/config/lirc-web:/root \
           flochtililoch/rpi-lirc-web
```