# syntax=docker/dockerfile:1.4.1
ARG BASE_IMAGE_VERSION
FROM ghcr.io/moba1/devcontainers/base/ubuntu:$BASE_IMAGE_VERSION
ENV DEBIAN_FRONTEND noninteractive

ARG USERNAME=editor
ARG USER_UID=1001
ARG USER_GID=$USER_UID

RUN <<EOF
groupadd --gid $USER_GID $USERNAME
useradd --uid $USER_UID --gid $USER_GID -m -s /bin/bash $USERNAME
apt-get update
apt-get install -y sudo
echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME
chmod 0440 /etc/sudoers.d/$USERNAME
EOF

WORKDIR /home/$USERNAME
USER $USERNAME
ENV USER $USERNAME

RUN <<EOF
sudo apt-get install -y xz-utils
bash -c 'sh <(curl -L https://nixos.org/nix/install) --no-daemon'
echo 'if [ -e ~/.nix-profile/etc/profile.d/nix.sh ]; then . ~/.nix-profile/etc/profile.d/nix.sh; fi' > .bashrc
bash -c '. .bashrc && nix-channel --add https://nixos.org/channels/nixpkgs-unstable nixpkgs'
bash -c '. .bashrc && nix-channel --update'
EOF

ENTRYPOINT [ "/usr/bin/bash", "-il" ]