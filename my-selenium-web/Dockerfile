ARG VERSION=slim
FROM node:${VERSION:-slim}
RUN mkdir -p /usr/src/app/src/public/js
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY src/*.js ./src/
COPY src/public/*.html ./src/public/
COPY src/public/js/*.js ./src/public/js/
EXPOSE 8080
CMD ["node","src/index.js"]
