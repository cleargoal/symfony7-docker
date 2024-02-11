# 🐳 Docker with Nginx, MySQL 8, PHP 8.2 (or 8.3), Symfony 7.0 Boilerplate

## Description

This is a complete stack for running Symfony 6.2 into Docker containers using a docker-compose tool.

It is composed of 3 containers:

- `nginx`, acting as the webserver.
- `php`, the PHP-FPM container with the 8.2 (8.3) version of PHP.
- `db` is the MySQL database container with a **MySQL 8.0** image.

## Installation

1. 😀 Clone this repo.

2. If you are working with Docker Desktop for Mac, ensure **you have enabled `VirtioFS` for your sharing implementation**. `VirtioFS` brings improved I/O performance for operations on bind mounts. Enabling VirtioFS will automatically enable the Virtualization framework.

3. Create the file `./.docker/.env.nginx.local` using `./.docker/.env.nginx` as template. The value of the variable `NGINX_BACKEND_DOMAIN` is the `server_name` used in NGINX.

4. Go inside the folder `./docker` and run `docker-compose up -d` to start containers.

5. You should work inside the `php` container. This project is configured to work with [Remote Container](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension for Visual Studio Code, so you could run the `Reopen in container` command after opening the project.

6. Inside the `php` container, run `composer install` to install dependencies into the `/var/www/symfony/vendor` folder.

7. Use the following value for the DATABASE_URL environment variable:

```
DATABASE_URL=mysql://app_user:helloworld@db:3306/app_db?serverVersion=8.0.33
```

### You could change the database's name, user, and password in the `env` file at the project's root.

## To learn more

The author (ger86) has recorded a YouTube session explaining the different parts of this project. You can see it here:

[Boilerplate para Symfony basado en Docker, NGINX y PHP8](https://youtu.be/A82-hry3Zvw)
