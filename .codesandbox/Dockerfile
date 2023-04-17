FROM ghcr.io/gbraad/devenv/base:37


USER root

RUN  dnf install -y podman \
     && dnf update -y tailscale \
     && dnf clean all \
     && rm -rf /var/cache/yum

# graphical
RUN dnf install -y \
        novnc \
        x11vnc \
        xrdp \
        i3 \
        python3-i3ipc \
        feh \
        tigervnc-server \
    && dnf clean all \
    && rm -rf /var/cache/yum
    && echo PREFERRED=i3 | tee /etc/sysconfig/desktop

USER gbraad

RUN git clone https://github.com/gbraad/dotfiles ~/.dotfiles \
    && ~/.dotfiles/install.sh
