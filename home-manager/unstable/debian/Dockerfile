# syntax=docker/dockerfile:1.4.1
ARG BASE_IMAGE_VERSION
FROM ghcr.io/moba1/devcontainers/nix/unstable/debian:$BASE_IMAGE_VERSION

RUN <<EOF
bash -c '. .bashrc && nix-channel --add https://github.com/nix-community/home-manager/archive/master.tar.gz home-manager'
bash -c '. .bashrc && nix-channel --update'
bash -c '. .bashrc && nix-shell --run sh "<home-manager>" -A install'
EOF
