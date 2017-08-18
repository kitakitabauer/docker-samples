FROM node:8.4.0-alpine

LABEL maintainer "kitakitabauer <kitakita.d.kitakita@gmail.com>"

ENV PM2_VERSION 2.6.1

RUN mkdir -p /usr/src/app\
 && apk add --no-cache bash git openssh

WORKDIR /usr/src/app

ARG NODE_ENV
ENV NODE_ENV $NODE_ENV
COPY package.json package-lock.json /usr/src/app/
RUN npm i pm2@${PM2_VERSION} -g && npm i
COPY . /usr/src/app

EXPOSE 5000

CMD ["pm2-docker", "index.js", "-i", "0"]

