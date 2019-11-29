FROM debian:buster
LABEL description="This image is used to run i2pd on a Debian Buster container"
LABEL maintainer="git@sexybiggetje.nl"

RUN set -ex \
  && apt update \
  && apt install -f -y curl \
  && curl -Lo i2pd.deb https://github.com/PurpleI2P/i2pd/releases/download/2.29.0/i2pd_2.29.0-1buster1_amd64.deb \
  && apt install -f -y ./i2pd.deb \
  && rm -f i2pd.deb \
  && apt remove -f -y curl \
  && apt autoremove -f -y

EXPOSE 7070 7656 4444 4447
ENTRYPOINT ["i2pd","--service","--http.address=0.0.0.0","--httpproxy.address=0.0.0.0","--socksproxy.address=0.0.0.0","--sam.address=0.0.0.0","--http.strictheaders=0","--nat=1","--upnp.enabled=1"]