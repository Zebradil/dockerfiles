FROM archlinux:latest

ARG PACMAN_MIRROR

RUN echo "Server = ${PACMAN_MIRROR}" > /etc/pacman.d/mirrorlist
RUN sed -i 's/^#Color$/Color/' /etc/pacman.conf

RUN pacman -Sy \
 && pacman -S --noconfirm \
        git \
        go \
        base-devel \
        openssh

RUN useradd -m aur \
 && echo 'aur ALL = NOPASSWD: /usr/bin/pacman' >> /etc/sudoers

USER aur

WORKDIR /home/aur

RUN git clone https://aur.archlinux.org/yay.git \
 && cd yay \
 && makepkg -si --noconfirm \
 && cd .. \
 && rm -rf yay

RUN sudo pacman -S --noconfirm vim
