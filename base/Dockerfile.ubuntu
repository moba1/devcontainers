ARG UBUNTU_VERSION
FROM ubuntu:$UBUNTU_VERSION
LABEL org.opencontainers.image.source=https://github.com/moba1/devcontainers

ENV DEBIAN_FRONTNED noninteractive
RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y curl git
