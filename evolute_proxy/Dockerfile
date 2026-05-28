//ARG BUILD_FROM=ghcr.io/home-assistant/aarch64-base-python:3.12-alpine3.21

ARG BASE_IMAGE=ghcr.io/home-assistant/base
ARG BASE_VERSION=3.23
ARG BUILD_FROM=${BASE_IMAGE}:${BASE_VERSION}

FROM ${BUILD_FROM}

ENV LANG=C.UTF-8

RUN apk add --no-cache \
        python3 \
        py3-pip \
    && pip3 install --no-cache-dir --upgrade pip \
    && pip3 install --no-cache-dir flask requests

COPY run.sh /run.sh
COPY evolute_api.py /evolute_api.py

RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
