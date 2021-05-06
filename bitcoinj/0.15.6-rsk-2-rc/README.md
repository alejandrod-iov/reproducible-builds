# BitcoinJ 0.15.6-rsk-2-rc

* Source: https://github.com/rsksmart/bitcoinj
* Tag: `TBD`

## Build

```
$ docker build -t bitcoinj-0.15.6-rsk-2-rc . --no-cache
```

## Verify

```
$ docker run --rm bitcoinj-0.15.6-rsk-2-rc sha256sum /code/bitcoinj/core/build/libs/bitcoinj-core-0.15.6-rsk-2-rc.jar
2dfa7e0e797cc61c5503768d6cad84851eea3bcbecfb08ed35033ae1f391505d  /code/bitcoinj/core/build/libs/bitcoinj-core-0.15.6-rsk-2-rc.jar
```

## (Optional) Extract JAR from image

```
$ docker run --name temp-container bitcoinj-0.15.6-rsk-2-rc /bin/true
$ docker cp temp-container:/code/bitcoinj/core/build/libs/bitcoinj-core-0.15.6-rsk-2-rc.jar ./bitcoinj-core-0.15.6-rsk-2-rc.jar
$ docker cp temp-container:/code/bitcoinj/core/build/libs/bitcoinj-core-0.15.6-rsk-2-rc.pom ./bitcoinj-core-0.15.6-rsk-2-rc.pom
$ docker rm temp-container
```
