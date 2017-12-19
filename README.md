# Wordpress Dockerized Environment
[![PRs Welcome][prs-badge]][prs]

This repository aims to simplify the setting up of a docker-compose development environment.

## Pre-requirements
Before whatever, make sure you have the latest versions of **Docker** and **Docker Compose** installed on your machine.
- [Docker](https://docs.docker.com/engine/installation/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## From a new project

- [Download](https://wordpress.org/latest.zip) latest WordPress version.
- Unzip `wordpress-x.x.x.zip` archive.
- Move all files present in the unzipped folder to `src/`
- Run `docker-compose up`.

## From an existing project
- Move all your files to `src/`.
- Copy the SQL dump file to `docker/dump/`.
- Update database credentials in `docker-compose.yml` with your own values.
- Run `docker-compose up`.


## Utils

### Docker Compose

```
# To start/restart your containers
$ docker-compose up

# To start/restart your containers in background
$ docker-compose up -d

# To stop all containers
$ docker-compose stop

# To stop and remove all containers
$ sudo docker-compose down

# To remove all stoped containers
$ docker-compose rm --all

# To connect you into wordpress container
$ docker-compose exec wordpress /bin/bash

# To connect you into mysql container
$ docker-compose exec mydb.mysql.db /bin/bash
```

### Wordpress

To override the hostname without changing any data in your database add in your **wp-config.php** the below lines:
```
define('WP_HOME','http://wordpress.local');
define('WP_SITEURL','http://wordpress.local');
```

### Scripts
```
# To dump MySQL 
$ bash utils/dump.sh
```


[prs-badge]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square
[prs]: http://makeapullrequest.com