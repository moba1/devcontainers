ARG BASE_IMAGE_TAG
FROM debian:$BASE_IMAGE_TAG
LABEL org.opencontainers.image.source=https://github.com/moba1/devcontainers

ENV DEBIAN_FRONTNED noninteractive
RUN <<EOF
apt-get update
apt-get upgrade -y
apt-get install -y curl git
EOF