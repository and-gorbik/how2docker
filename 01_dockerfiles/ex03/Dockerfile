FROM ubuntu:16.04

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y ca-certificates openssh-server wget postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && \
	bash script.deb.sh && \
	apt-get update && apt-get install -y gitlab-ce

RUN apt update && apt install -y tzdata

EXPOSE 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# docker-machine create --driver virtualbox --virtualbox-cpu-count "2" --virtualbox-memory "4096" gitlab-host
# eval $(docker-machine env gitlab-host)
# docker build -t gitlab .
# docker run -it --rm -p 8080:80 -p 8022:22 gitlab
