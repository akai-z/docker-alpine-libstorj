FROM alpine:3.8 AS builder

LABEL maintainer="Ammar K." \
      stage=intermediate

ARG VERSION=tags/v1.0.3
ARG REPOSITORY=storj/libstorj
ARG BUILDER_URL=https://raw.githubusercontent.com/akai-z/libstorj-alpine-source-builder/master/libstorj-alpine-source-builder.sh

ADD $BUILDER_URL /usr/local/bin

RUN set -x \
    && chmod +x /usr/local/bin/libstorj-alpine-source-builder.sh \
    && libstorj-alpine-source-builder.sh \
        -build_deps_install \
        --repository="$REPOSITORY" \
        --version="$VERSION" \
    && libstorj-alpine-source-builder.sh \
        clean

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
