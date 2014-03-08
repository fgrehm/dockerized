# proxy

[Polipo](http://www.pps.univ-paris-diderot.fr/~jch/software/polipo/) in a container

## Building image

```sh
git clone https://github.com/fgrehm/dockerized.git
cd dockerized/proxy
docker build -rm -t fgrehm/proxy .
```

## Running proxy

```sh
docker run -d -p 3128:3128 -name=proxy fgrehm/proxy
```

## Removing proxy container

```sh
docker rm -v proxy
```
