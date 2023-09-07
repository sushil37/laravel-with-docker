# Welcome to the Laravel Dockerized Project! 🚀

This repository contains a Dockerized Laravel project setup for your convenience. Follow these simple steps to get started:

## Clone the Repository
```bash
git clone <repository-url>
cd repo-name
```

## Install Laravel
Use this one-liner to install Laravel and move all files/folders to the root folder:
```bash
curl -s https://laravel.build/example-app | bash
shopt -s dotglob
mv example-app/* .
```

## Follow the Steps

1. **Dockerfile**: Contains basic Docker configuration for the Laravel project setup with the PHP version you need.

2. **docker-compose/nginx**: Docker Compose configuration for the Nginx server.

3. **docker-compose/nginx/laravel.conf**: Nginx server configuration.

4. **docker-compose/mysql**: Docker Compose configuration for MySQL.

5. **docker-compose/mysql/init_db.sql**: Load basic default data if needed (remove or comment out if not).

## Update Docker Compose Configuration
Don't forget to update the `container_name` for each app, db, and nginx service in the `docker-compose.yml` file.

## Run Docker
Here's what each Docker command does:

```bash
# Build the Docker containers
docker-compose build app

# Start the Docker containers in detached mode
docker-compose up -d

# List running containers
docker-compose ps

# List files and folders in the app container
docker-compose exec app ls -l

# Remove the vendor directory and composer.lock file (if present)
docker-compose exec app rm -rf vendor composer.lock

# Install Composer dependencies
docker-compose exec app composer install

# Generate a Laravel application key
docker-compose exec app php artisan key:generate
```

## Deploy
Access your Laravel application at:
```plaintext
http://server_domain_or_IP:8000
```

Enjoy exploring your Dockerized Laravel project! If you have any questions or need further assistance, feel free to reach out. 🎉
