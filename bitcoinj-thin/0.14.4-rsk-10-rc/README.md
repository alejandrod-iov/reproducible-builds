# BitcoinJ 0.14.4-rsk-10-rc

* Source: https://github.com/rsksmart/bitcoinj-thin
* Tag: `v0.14.4-rsk-10-rc`

## Build

```
$ docker build -t bitcoinj-thin-0.14.4-rsk-10-rc .
```

## Verify

```
$ docker run --rm bitcoinj-thin-0.14.4-rsk-10-rc sha256sum /code/bitcoinj-thin/target/bitcoinj-thin-0.14.4-rsk-10-rc.jar
033a3386d27f2f20cf5aa997d3ea98e0070c796eb9cb1035f5820eee2a049654  /code/bitcoinj-thin/target/bitcoinj-thin-0.14.4-rsk-10-rc.jar

$ docker run --rm bitcoinj-thin-0.14.4-rsk-10-rc sha256sum /code/bitcoinj-thin/pom.xml
cc0f88b7339d309fc49efe0b51729e92e942ec85387c5f627a8eee283a6bb7b4  /code/bitcoinj-thin/pom.xml
```

## (Optional) Extract JAR from image

```
$ docker run --name temp-container bitcoinj-thin-0.14.4-rsk-10-rc /bin/true
$ docker cp temp-container:/code/bitcoinj-thin/target/bitcoinj-thin-0.14.4-rsk-10-rc.jar ./bitcoinj-thin-0.14.4-rsk-10-rc.jar
$ docker cp temp-container:/code/bitcoinj-thin/pom.xml ./bitcoinj-thin-0.14.4-rsk-10-rc.pom
$ docker rm temp-container
```
