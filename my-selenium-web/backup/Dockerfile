ARG VERSION=slim
FROM node:${VERSION:-slim}
RUN mkdir -p /var/www/html
WORKDIR /var/www/html

VOLUME ./var/www/html /var/www/html
COPY ./var/www/html/package*.json ./
COPY ./var/www/html/*.js ./
COPY ./var/www/html/*.html ./
RUN npm install

EXPOSE 8080
CMD [ "node", "server" ]
