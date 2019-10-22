FROM debian:bullseye-slim

RUN apt-get update && apt-get install -y \
	nmap --no-install-recommends && \
	rm -rf /var/lib/apt/lists/*

ENV IP=8.8.8.8
ENV FLAGS=-sT

ENTRYPOINT nmap $FLAGS $IP
