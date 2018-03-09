# !!NOTE!!
This Image **do not** contain any piece of Gitscrum, just dockerized Laravel toolkits.

To deploy Gitscrum with this image, follow these steps:

```
$ git clone https://github.com/ye-will/docker-gitscrum.git
$ cd docker-gitscrum
$ git clone https://github.com/gitscrum-community-edition/laravel-gitscrum.git ./www/laravel-gitscrum # checkout the source of Gitscrum
$ docker-compose up -d
$ docker exec -it dockergitscrum_phpfpm-gitscrum_1 /bin/sh
```

Then you will attach into a container of **this** image. After that,

```
$ cd /www/laravel-gitscrum
$ composer update
$ composer run-script post-root-package-install
```

Finally, edit .env file under the Setup Guide of https://github.com/gitscrum-community-edition/laravel-gitscrum, with db config declared in docker-compose.yml

```
DB_CONNECTION=mysql
DB_HOST=mysql-gitscrum
DB_PORT=3306
DB_DATABASE=develop
DB_USERNAME=gitscrum
DB_PASSWORD=123456
```

Congratulations, now you get Gitscrum at http://localhost

# Docker-GitScrum
Docker containers for Laravel GitScrum

# Build Containers
You can run the command on your bash to build the containers

```
docker-compose up --build
```

# How to install Docker Compose
[Docker Compose](https://docs.docker.com/compose/install/)

