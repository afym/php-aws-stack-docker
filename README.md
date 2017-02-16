# php-aws-stack-docker

This project lets you develop web applications base on PHP 7.0 over php-fpm and nginx using pos

### Requirements
* You must have installed **docker engine**
* You must have installed **docker compose**

### Components

* local_php_application
  * host : default.web.app
  * port : 80
  * external port : 8090
* local_memcached_server
  * host : memcached
  * port : 11211
  * external port : 8091
* local_postgresql_server
  * host : postgresql
  * user : postgres_user
  * pass : postgres_password
  * port : 5432
  * external port : 8092

### Running the environment

```
$ docker-compose up
```

### Inspect the containers

```
$ docker ps
$ docker exec -ti <container-id> bash
```

### Changing base image

```
$ docker-compose build
```
