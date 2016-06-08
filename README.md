# Typesafe Activator binary

From JDK - Alpine image, built automatically

[![](https://badge.imagelayers.io/edwxie/activator:latest.svg)](https://imagelayers.io/?images=edwxie/activator:latest 'Get your own badge on imagelayers.io')

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
docker run --rm -it -v ivy2:/root/.ivy2 -v sbt:/root/.sbt -v "$(pwd)":/code edwxie/activator compile
```
