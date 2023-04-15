FROM ghcr.io/gbraad/devenv/base:37


USER root

RUN  dnf update tailscale \
     && dnf clean all \
     && rm -rf /var/cache/yum

USER gbraad

RUN git clone https://github.com/gbraad/dotfiles ~/.dotfiles \
    && ~/.dotfiles/install.sh
