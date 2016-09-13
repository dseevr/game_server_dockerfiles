# image name: billrobinson/steamcmd
FROM ubuntu:16.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get -y install lib32gcc1 curl
RUN apt-get -y autoclean
RUN apt-get -y autoremove

RUN useradd -m steam

USER steam
WORKDIR /home/steam

RUN curl -sqL 'https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz' | tar zxvf -

ENTRYPOINT ["/bin/bash"]
