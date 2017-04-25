# docker-shadowsocks-libev

A Docker image that contains shadowsocks-libev service.

The image is pretty small(~12MB) because it uses Alpine the base image.

## How to build the image

Before you build the image, you can modify the environment variable `SHADOWSOCKS_VERSION` in the Dockerfile to specify the version of shadowsocks-libev that you want, then run the follwing command to build it.

```shell
docker build \
    -t er1cst/shadowsocks-libev:v3.0.4 \
    --no-cache \
    .
```

## how to use this image

Because 8388 is the port that the container exposes, when you publish the shadowsocks service, you should publish port 8388 using `-p` parameter in `docker run`.

Then run the follwing command, which creates an instance of shadowsocks-libev server.

```shell
docker run \
    -d \
    -p 12849:8388/tcp \
    -p 12849:8388/udp \
    er1cst/shadowsocks-libev:v3.0.4 \
        ss-server \
            -p 8388 \
            -k 'ZG5B4GqrXS8avcc2' \
            -u \
            -m 'chacha20-ietf'
```

