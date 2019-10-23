FROM debian:bullseye-slim

RUN apt-get update && apt-get install -y \
	nginx openssl --no-install-recommends && \
	rm -rf /var/lib/apt/lists/*

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -subj "/C=RU/ST=IDF/O=School21/OU=roger/CN=localhost" \
	-keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt
RUN openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048
COPY self-signed.conf /etc/nginx/snippets/self-signed.conf
COPY ssl-params.conf /etc/nginx/snippets/ssl-params.conf
COPY nginx.conf /etc/nginx/sites-available/default

RUN nginx -t

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log

WORKDIR /web
COPY www/. .
RUN chown -R www-data:www-data .
RUN pwd && ls -la

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
