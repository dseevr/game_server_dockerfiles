# image name: billrobinson/steamcmd
FROM ubuntu:12.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get -y install curl lib32asound2 lib32gcc1 lib32ncurses5 lib32z1 lib32bz2-1.0

RUN useradd -m steam

RUN curl -sqL -o /home/steam/steam.tar.gz 'https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz'
RUN chown steam:steam /home/steam/steam.tar.gz

RUN apt-get -y remove curl
RUN apt-get -y autoremove
RUN apt-get -y autoclean
RUN rm -rf /var/lib/apt/lists/*

USER steam
WORKDIR /home/steam

RUN tar xfvz steam.tar.gz
RUN rm steam.tar.gz

ENTRYPOINT ["/bin/bash"]
