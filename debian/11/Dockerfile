FROM debian:buster

ENV PGROONGA_VERSION=2.2.6-1
RUN \
  apt update && \
  apt install -y wget && \
  wget https://packages.groonga.org/debian/groonga-archive-keyring-latest-buster.deb && \
  apt install -y -V ./groonga-archive-keyring-latest-buster.deb && \
  apt update && \
  apt install -y \
    postgresql-11-pgroonga=${PGROONGA_VERSION} \
    groonga-tokenizer-mecab && \
  apt clean && \
  rm -rf /var/lib/apt/lists/*

COPY entrypoint.sh /entrypoint.sh

EXPOSE 5432
ENTRYPOINT ["/entrypoint.sh"]
