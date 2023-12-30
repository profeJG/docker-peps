ARG VERSION=slim
FROM node:${VERSION:-slim}
RUN mkdir -p /usr/src/app/www/public
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY src/*.js ./www/
COPY src/public/*.html ./www/public/
EXPOSE 8080
CMD ["node","www/index.js"]
