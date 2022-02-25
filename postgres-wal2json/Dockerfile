FROM postgres:14-alpine3.15

LABEL maintainer aanogueira@protonmail.com

ENV WAL2JSON_COMMIT_ID=wal2json_2_3

RUN apk add git make gcc musl-dev clang llvm

RUN git clone https://github.com/eulerto/wal2json -b master --single-branch \
    && cd /wal2json \
    && git checkout $WAL2JSON_COMMIT_ID \
    && make && make install \
    && cd / \
    && rm -rf wal2json \
    && apk del git make gcc musl-dev clang llvm

CMD [ "postgres", "-c", "wal_level=logical" ]
