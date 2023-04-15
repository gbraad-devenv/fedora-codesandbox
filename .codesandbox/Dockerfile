FROM ghcr.io/gbraad/devenv/base:37

USER root

RUN  dnf config-manager --add-repo https://pkgs.tailscale.com/stable/fedora/tailscale.repo \
     && dnf install tailscale \
     && dnf clean all \
     && rm -rf /var/cache/yum

USER gbraad

RUN git clone https://github.com/gbraad/dotfiles ~/.dotfiles \
    && ~/.dotfiles/install.sh
