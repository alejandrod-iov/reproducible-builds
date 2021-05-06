FROM openjdk:8u171

RUN apt update
RUN apt install -y --no-install-recommends file unzip maven git strip-nondeterminism

RUN git clone --single-branch --depth 1 --branch fix-checkpoints https://github.com/rsksmart/bitcoinj.git /code/bitcoinj

WORKDIR /code/bitcoinj

RUN ./gradlew clean build -x test
RUN strip-nondeterminism ./core/build/libs/bitcoinj-core-0.15.6-rsk-2-rc.jar