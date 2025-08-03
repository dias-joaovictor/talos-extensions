FROM alpine:3.20 AS build
RUN apk add --no-cache cifs-utils keyutils \
 && mkdir -p /ext/rootfs/usr/{sbin,bin} \
 # copy whatever path the binaries are in *this* image
 && cp $(command -v mount.cifs)      /ext/rootfs/usr/sbin/ \
 && cp $(command -v cifs.upcall)     /ext/rootfs/usr/sbin/ \
 && cp $(command -v request-key)     /ext/rootfs/usr/sbin/ \
 && cp $(command -v keyctl)          /ext/rootfs/usr/bin/

FROM scratch
COPY manifest.yaml /
COPY --from=build /ext/ /