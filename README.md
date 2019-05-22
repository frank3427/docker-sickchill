# docker-sickchill
Install sickchill into a Linux container

![sickchill](https://sickchill.github.io/images/logo.png)

## Tag
Several tag are available:
* latest: see alpine
* centos7: [Dokerfile_centos7](https://github.com/digrouz/docker-sickchill/blob/master/Dockerfile_centos7)
* alpine: [Dockerfile_alpine](https://github.com/digrouz/docker-sickchill/blob/master/Dockerfile_alpine)

## Description

SickChill is an automatic Video Library Manager for TV Shows. It watches for new episodes of your favorite shows, and when they are posted it does its magic: automatic torrent/nzb searching, downloading, and processing at the qualities you want.

https://sickchill.github.io/

## Usage
    docker create --name=sickchill  \
      -v /etc/localtime:/etc/localtime:ro \ 
      -v <path to config>:/config \
      -v <path to downloads>:/downloads \ 
      -v <path to show library>:/tv \
      -v <path to anime library>:/animes \ 
      -e DOCKUID=<UID default:10000> \
      -e DOCKGID=<GID default:10000> \
      -e DOCKUPGRADE=<0|1> \
      -p 8081:8081 frank3427/sickchill:latest

## Environment Variables

When you start the `sickchill` image, you can adjust the configuration of the `sickchill` instance by passing one or more environment variables on the `docker run` command line.

### `DOCKUID`

This variable is not mandatory and specifies the user id that will be set to run the application. It has default value `10000`.

### `DOCKGID`

This variable is not mandatory and specifies the group id that will be set to run the application. It has default value `10000`.

### `DOCKUPGRADE`

This variable is not mandatory and specifies if the container has to launch software update at startup or not. Valid values are `0` and `1`. It has default value `0`.

## Notes

* The docker entrypoint can upgrade operating system at each startup. To enable this feature, just add `-e DOCKUPGRADE=1` at container creation.

## Issues

If you encounter an issue please open a ticket at [github](https://github.com/frank3427/docker-sickchill/issues)
