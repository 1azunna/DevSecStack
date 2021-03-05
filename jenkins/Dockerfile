FROM jenkins/jenkins:2.263.1-lts-alpine@sha256:ecb1380154ea6e7444324c2dc811da62b8c0d02034a553b4b457577a402bce01
USER root
RUN apk update \
    && apk add --no-cache  --repository http://dl-cdn.alpinelinux.org/alpine/edge/main \
    --repository  http://dl-cdn.alpinelinux.org/alpine/edge/community docker docker-compose \
    && rm -rf /var/cache/apk/* 

RUN addgroup jenkins docker \
    && rc-update add docker boot

RUN pip install truffleHog

USER jenkins
RUN jenkins-plugin-cli --plugins blueocean:1.24.3

