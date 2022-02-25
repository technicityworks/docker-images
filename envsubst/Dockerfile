FROM aanogueira/alpine:3.15.0

LABEL maintainer aanogueira@protonmail.com

RUN apk add --update libintl && \
    apk add --virtual build_deps gettext &&  \
    cp /usr/bin/envsubst /usr/local/bin/envsubst && \
    apk del build_deps

USER 10001
