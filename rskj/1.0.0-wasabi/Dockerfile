FROM ubuntu:16.04

RUN apt-get update -y && \
    apt-get install -y git curl gnupg-curl openjdk-8-jdk=8u212-b03-0ubuntu1.16.04.1 && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get autoremove -y && \
    apt-get clean

RUN gpg --keyserver https://secchannel.rsk.co/release.asc --recv-keys 1A92D8942171AFA951A857365DECF4415E3B8FA4
RUN gpg --finger 1A92D8942171AFA951A857365DECF4415E3B8FA4

RUN git clone --single-branch --depth 1 --branch WASABI-1.0.0 https://github.com/rsksmart/rskj.git /code/rskj

WORKDIR /code/rskj

RUN gpg --verify SHA256SUMS.asc
RUN sha256sum --check SHA256SUMS.asc
RUN ./configure.sh
RUN ./gradlew clean build -x test
