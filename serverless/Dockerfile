FROM node:6-alpine

LABEL maintainer="Adam Ross <grayside+dockerfiles@gmail.com>"

WORKDIR /app

ENV PATH=/root/.yarn/bin:/usr/local/bin/:$PATH \
    YARN_CACHE_FOLDER=/cache/yarn

ARG SERVERLESS_VERSION=1.26.0

RUN apk add --update --no-cache git openssl curl

RUN mkdir -p /cache/yarn && \
    yarn global add serverless@$SERVERLESS_VERSION && \
    yarn cache clean
