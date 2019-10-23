FROM debian

ENV MSG=hello
RUN apt-get update && apt-get install -y cowsay
ENTRYPOINT echo $MSG | /usr/games/cowsay
