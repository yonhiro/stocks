# docker-laravel 🐳

![License](https://img.shields.io/github/license/shipwebdotjp/docker-laravel?color=f05340)
![Stars](https://img.shields.io/github/stars/shipwebdotjp/docker-laravel?color=f05340)
![Issues](https://img.shields.io/github/issues/shipwebdotjp/docker-laravel?color=f05340)
![Forks](https://img.shields.io/github/forks/shipwebdotjp/docker-laravel?color=f05340)

## Introduction

Build a simple laravel development environment with docker-compose.  
Supported version: Laravel 10

## Usage

```bash
$ git clone git@github.com:shipwebdotjp/docker-laravel.git
$ cd docker-laravel
$ make create-project # Install the latest Laravel project
$ make install-recommend-packages # Not required
```

http://localhost

Read this [Makefile](https://github.com/shipwebdotjp/docker-laravel/blob/master/Makefile).

## Tips

Read this [Wiki](https://github.com/shipwebdotjp/docker-laravel/wiki).

## Container structure

```bash
├── app
├── web
└── db
```

### app container

- Base image
  - [php](https://hub.docker.com/_/php):8.1-fpm-buster
  - [composer](https://hub.docker.com/_/composer):2.2

### web container

- Base image
  - [nginx](https://hub.docker.com/_/nginx):1.24-alpine
  - [node](https://hub.docker.com/_/node):20-alpine

### db container

- Base image
  - [mysql](https://hub.docker.com/_/mysql):8.0

#### Persistent MySQL Storage

By default, the [named volume](https://docs.docker.com/compose/compose-file/#volumes) is mounted, so MySQL data remains even if the container is destroyed.
If you want to delete MySQL data intentionally, execute the following command.

```bash
$ docker-compose down -v && docker-compose up
```
