FROM debian:10.1

ENV TS3SERVER_LICENSE=accept
EXPOSE 9987/udp 30033 10011

RUN apt-get update && \
    apt-get install wget bzip2 -y

RUN useradd -m teamspeak
WORKDIR /home/teamspeak

ARG VERSION=3.1.2
ARG TS3SERVER=teamspeak3-server_linux_amd64
RUN wget http://dl.4players.de/ts/releases/$VERSION/$TS3SERVER-$VERSION.tar.bz2 && \
    tar xf $TS3SERVER-$VERSION.tar.bz2 && \
    rm -r $TS3SERVER-$VERSION.tar.bz2
WORKDIR $TS3SERVER
ENTRYPOINT ./ts3server_minimal_runscript.sh
