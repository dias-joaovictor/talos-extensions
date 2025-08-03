FROM alpine:3.20
RUN apk add --no-cache samba-client cifs-utils

# copy only the bits you want Talos to get
RUN mkdir -p /rootfs/usr/bin \
    && cp /usr/bin/mount.cifs /rootfs/usr/bin \
    && strip /rootfs/usr/bin/mount.cifs

COPY manifest.yaml /