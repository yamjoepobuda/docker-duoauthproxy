FROM alpine:3.7

RUN apk upgrade --update --available && \
    apk add \
      bash \
      curl \
      python \
      gcc \
      gmp-dev \
      libc-dev \
      libffi-dev \
      libgcc \
      'libressl-dev>=2.6.3-r0' \
      linux-headers \
      make \
      patch \
      py-setuptools \
      python-dev \
      tar \
      zlib-dev \
    && rm -f /var/cache/apk/* && \
    adduser -D duo

ARG VERSION

# Build and install authproxy.
ADD https://dl.duosecurity.com/duoauthproxy-${VERSION}-src.tgz /root/
COPY build /root/
RUN /root/build
