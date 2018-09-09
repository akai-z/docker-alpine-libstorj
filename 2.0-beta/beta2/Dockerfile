FROM alpine:3.8 AS builder

LABEL maintainer="Ammar K." \
      stage=intermediate

ARG VERSION=tags/v2.0.0-beta2
ARG REPOSITORY=storj/libstorj

ENV SOURCE=https://api.github.com/repos/${REPOSITORY}/releases/${VERSION} \
    SOURCE_DIR=libstorj \
    TMPDIR=/tmp/

RUN set -x \
    && apk update \
    && apk add -u --no-cache --virtual .build-deps \
        autoconf \
        automake \
        curl \
        curl-dev \
        g++ \
        json-c-dev \
        libmicrohttpd-dev \
        libtool \
        libuv-dev \
        make \
        nettle-dev \
    && mkdir $SOURCE_DIR \
    && cd $SOURCE_DIR \
    && curl $SOURCE \
        | grep "tarball_url" \
        | cut -d '"' -f 4 \
        | xargs curl -L \
        | tar -zx --strip 1 \
    && mkdir -p build-aux/m4 \
    && ./autogen.sh \
    && ./configure \
    && make \
    && make install \
    && ./test/tests \
    && cd .. \
    && rm -rf $SOURCE_DIR ${TMPDIR}* \
    && apk del .build-deps

FROM alpine:3.8

LABEL maintainer="Ammar K."

RUN set -x \
    && apk update \
    && apk add -u --no-cache \
        json-c \
        libcurl \
        libuv \
        nettle

COPY --from=builder /usr/local/bin/storj /usr/local/bin/storj
