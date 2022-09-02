# Docker Hub
[https://hub.docker.com/repository/docker/dschreck/laravel-spatie-composer](https://hub.docker.com/repository/docker/dschreck/laravel-spatie-composer)

# About
When using [Laravel](https://laravel.com/) and [Sail](https://laravel.com/docs/9.x/sail#main-content) it's preferred to avoid installing PHP and composer locally. This can be solved by using composer directly from Docker Hub.

The gotcha here is when you'd like to also use [Spatie's laravel-medialibrary](https://github.com/spatie/laravel-medialibrary). As it asks for some additional libraries to be installed. 

This is my quick hack solution to it.

Other's may have better ones, but this is mine 🤷

# Use
```shell
# change director to your local fresh checkout (sans `vendor` folder)
docker run --rm \
    -v "$(pwd)":/app \
    -w /app \
    dschreck/laravel-spatie-composer:latest \
    composer install
```

# Rebuild
```shell
# build
docker build -t dschreck/laravel-spatie-composer .

# login to docker
docker login

# push
docker push dschreck/laravel-spatie-composer:latest
```
