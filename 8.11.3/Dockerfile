FROM node:16.11.1-alpine@sha256:417b3856d2e5d06385123f3924c36f5735fb1f690289ca69f2ac9c35fd06c009

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
