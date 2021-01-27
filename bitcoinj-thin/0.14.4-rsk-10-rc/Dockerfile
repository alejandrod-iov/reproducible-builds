FROM openjdk:8u171

RUN apt update
RUN apt install -y --no-install-recommends file unzip maven git strip-nondeterminism

RUN git clone --single-branch --depth 1 --branch 0.14.4-rsk-10-rc https://github.com/rsksmart/bitcoinj-thin.git /code/bitcoinj-thin

WORKDIR /code/bitcoinj-thin

RUN mvn clean package -DskipTests
RUN strip-nondeterminism ./target/bitcoinj-thin-0.14.4-rsk-10-rc.jar
