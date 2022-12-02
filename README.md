
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Deploy Wordpress on Localhost and in Production using Docker Compose

Related blog post:

  - [WordPress Local Development Using Docker
    Compose](https://www.datanovia.com/en/lessons/wordpress-local-development-using-docker-compose/):
    Deploy Wordpress on localhost using docker
  - [Docker WordPress Production
    Deployment](https://www.datanovia.com/en/lessons/docker-wordpress-production-deployment/):
    Step-by-step guide to deploy WordPress online using docker-compose
  - [Using Docker WordPress Cli to Manage WordPress
    Websites](https://www.datanovia.com/en/lessons/using-docker-wordpress-cli-to-manage-wordpress-websites/):
    Commande line interface for managing a WordPress website

The installation tool kit, provided here, include:

  - Nginx web server
  - MariaDB/MySQL used for Wordpress database
  - phpMyAdmin interface to connect to your MySQL database
  - WP-Cli: Wordpress Command Line Interface
  - Makefile directives for automatization.

You can automatically deploy a local docker wordpress site in 5 minutes
using the following commands:

``` bash
cd wordpress-docker-compose
# Build and start installation
docker-compose up -d --build
```

Visit your site at <http://localhost:PORT> and your database via phpMyAdmin
at <http://localhost:PHPMYADMIN_PORT>.

Default identification for your wordpress website admin:

  - `Username: admin` and
  - `Password: admin`

Default identification for the phpMyAdmin interface:

  - `Username: root` and
  - `Password: password`

In order to install plguins use the wpcli, for example Woocommerce

``` bash
docker-compose run --rm wpcli plugin install woocommerce --activate
docker-compose run --rm wpcli plugin install jwt-auth --activate       
docker-compose run --rm wpcli plugin install jwt-authentication-for-wp-rest-api --activate

```

**Useful set of commands to know**:

``` bash
# Stop and remove containers
docker-compose down
# Build, and start the wordpress website
docker-compose up -d --build
# Reset everything
docker-compose down
rm -rf certs/* certs-data/* logs/nginx/* mysql/* wordpress/*
```

## References

  - [WordPress: with Nginx web server in
    Docker](https://github.com/mjstealey/wordpress-nginx-docker)
  - [Quickstart: Compose and
    WordPress](https://docs.docker.com/compose/wordpress/)
