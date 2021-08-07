# Quick Start

```
docker-compose up -d
```

This command will start a PHP/Apache and Mysql servers in docker.

Visit: http://localhost:8080

# PHP

## Version

PHP version can be configured in `.env`. After a change, make sure you run:

```
docker-compose up --build -d
```

## Extensions

To enable/disable extensions for PHP, modify `./php/Dockerfile` and comment
in/out the required extensions.

## Custom configuration

`./php/php.ini` can be used to add custom configuration to php.
Make sure you run `docker-compose restart webserver` to have the changes
reflected in the server.

# MySQL

## MySQL from PHP

```php
$conn = new mysqli('mysql', $_ENV['MYSQL_USER'], $_ENV['MYSQL_PASSWORD'], $_ENV['MYSQL_DATABASE']/*, 3306 */);
```

## MySQL from the host machine:

server: `127.0.0.1`
port: `33060`
user: `mysql-username`
password: `mysql-password`

user and password are defined in `.env`

