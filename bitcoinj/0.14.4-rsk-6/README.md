# BitcoinJ 0.14.4-rsk-6

* Source: https://github.com/rsksmart/bitcoinj
* Tag: `v0.14.4-rsk-6`

## Build

```
$ docker build -t bitcoinj-0.14.4-rsk-6 .
```

## Verify

```
$ docker run --rm bitcoinj-0.14.4-rsk-6 sha256sum /code/bitcoinj/core/target/bitcoinj-core-0.14.4-rsk-6.jar
091b2752c5ac8430c4c60a7842e7ded834c926c12e0ee4c94eb592248dcb1200 /code/bitcoinj/core/target/bitcoinj-core-0.14.4-rsk-6.jar
```

## (Optional) Extract JAR from image

```
$ docker run --name temp-container bitcoinj-0.14.4-rsk-6 /bin/true
$ docker cp temp-container:/code/bitcoinj/core/target/bitcoinj-core-0.14.4-rsk-6.jar ./bitcoinj-core-0.14.4-rsk-6.jar
$ docker cp temp-container:/code/bitcoinj/core/pom.xml ./bitcoinj-core-0.14.4-rsk-6.pom
$ docker cp temp-container:/code/bitcoinj/pom.xml ./bitcoinj-parent-0.14.4-rsk-6.pom
$ docker rm temp-container
```
