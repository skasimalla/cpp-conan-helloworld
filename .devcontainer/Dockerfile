#Sam Kasimalla
FROM alpine:latest

LABEL maintainer="Sam Kasimalla"

VOLUME "/project"

WORKDIR "/project"

RUN apk update && \
    apk upgrade && \
    apk --update add \
        gcc \
        g++ \
        build-base \
        cmake \
        bash \
        libstdc++ \
        cppcheck \
        py-pip && \
        pip install conan && \
    rm -rf /var/cache/apk/*


RUN conan profile new default --detect \
    && conan profile update settings.compiler.libcxx=libstdc++11 default    