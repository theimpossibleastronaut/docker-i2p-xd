FROM debian:bookworm
LABEL description="This image is used to run the XD bittorrent client on Debian Bookworm container"
LABEL maintainer="git@sexybiggetje.nl"

ADD torrents.ini /torrents.ini

RUN set -ex \
  && apt update \
  && apt install -f -y build-essential git golang \
  && git clone https://github.com/majestrate/XD XD \
  && cd XD \
  && make \
  && make install \
  && apt remove -f -y build-essential git

EXPOSE 1488
ENTRYPOINT ["XD","torrents.ini"]
VOLUME ["storage"]
