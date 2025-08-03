# Tiny helper base maintained by Sidero Labs
FROM ghcr.io/siderolabs/extensions:v1.10.5

# Install the helpers into /rootfs (inside the extension layer)
RUN apk add --no-cache cifs-utils keyutils

# Drop the manifest at the root of the image
COPY manifest.yaml /
