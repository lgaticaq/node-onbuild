FROM node:10.4.1-alpine@sha256:665c69f05591a87e07ee41cfc00c148311be90df4a2670c8031ed9e2bff0fff3

LABEL maintainer "Leonardo Gatica <lgatica@protonmail.com>"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD ARG NODE_ENV
ONBUILD ENV NODE_ENV $NODE_ENV
ONBUILD COPY package.json yarn.* /usr/src/app/
ONBUILD RUN if [ -e yarn.lock ]; \
  then yarn && yarn cache clean; \
  else npm i && npm cache clean --force; fi && \
  apk del build-dependencies && \
  rm -rf ~/.node-gyp /tmp/*
ONBUILD COPY . /usr/src/app

CMD [ "node", "index.js" ]
