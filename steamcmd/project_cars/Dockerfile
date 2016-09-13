# image name: billrobinson/project_cars_server
# default ports: -p 8766:8766/udp -p 27015:27015/udp -p 27016:27016
FROM billrobinson/steamcmd

RUN ./steamcmd.sh +login anonymous +force_install_dir ./pcars_ds +app_update 332670 validate +exit

EXPOSE 8766/udp
EXPOSE 27015/udp
EXPOSE 27015/udp

ENTRYPOINT ["./pcars_ds/DedicatedServerCmd"]
CMD ["-c", "server.cfg"]
