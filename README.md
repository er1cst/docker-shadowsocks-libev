# docker-shadowsocks-libev
--------

The image is pretty small(~12MB).

## How to build the image

```shell
docker build \
    -t er1cst/shadowsocks-libev:v3.0.4 \
    --no-cache \
    .
```

## how to use this image
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
