# tag name:	openjdk:8-jdk-slim-buster 
# retrieved:	Thu Sep  3 20:59:42 UTC 2020
FROM openjdk@sha256:335627a2118556b3f412287e08ac7febb8ecc46325dc6b3570db56f32d33938f

RUN apt-get update -y && \
    apt-get install -y git curl gnupg && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get autoremove -y && \
    apt-get clean

RUN gpg --keyserver https://secchannel.rsk.co/release.asc --recv-keys 1A92D8942171AFA951A857365DECF4415E3B8FA4
RUN gpg --finger 1A92D8942171AFA951A857365DECF4415E3B8FA4

RUN git clone --single-branch --depth 1 --branch PAPYRUS-2.1.0.1 https://github.com/rsksmart/powpeg-node.git /code/powpeg-node

WORKDIR /code/powpeg-node

RUN gpg --verify SHA256SUMS.asc
RUN sha256sum --check SHA256SUMS.asc
RUN ./configure.sh
RUN ./gradlew --no-daemon clean build -x test

RUN sha256sum build/libs/*
