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

# docker build -t gitlab .
# docker run -it --rm -p 8080:80 -p 8022:22 --privileged gitlab
