# syntax=docker/dockerfile:1.2
ARG ARCH
ARG NAME
FROM $NAME-base:current-$ARCH
MAINTAINER Phusion <info@phusion.nl>

ADD . /pd_build

ARG ARCH
ARG http_proxy
RUN --mount=type=cache,target=/build_cache \
    /usr/bin/nice /pd_build/install_image.sh

CMD ["/sbin/my_init"]
EXPOSE 80 443
