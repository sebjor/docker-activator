# Typesafe Activator binary

From JDK - Alpine image, built automatically

[![](https://images.microbadger.com/badges/image/edwxie/activator.svg)](https://microbadger.com/images/edwxie/activator "Get your own image badge on microbadger.com")

## How to use

 - Create docker volume to store dependencies and libraries, so you don't need to download it everytime

```
docker volume create --name ivy2
docker volume create --name sbt
```

 - Go into your source code folder.
```
cd <source code folder>
```

 - Run any activator command in the following way (take compile for example):
```
docker run --rm -v ivy2:/root/.ivy2 -v sbt:/root/.sbt -v "$(pwd)":/code edwxie/activator activator compile
```
