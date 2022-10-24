<p align="center"><a href="https://www.multidialogo.it" target="_blank"><img src="https://github.com/Multidialogo/multidialogo-job-day-2022/blob/6138066f08f66549ec79f52a5928756387a12d34/public/logo-engineering.png" width="400" alt="Laravel Logo"></a></p>

## Requirements

- git
- docker, docker-compose

## First steps

```shell
# create .env file from .env.example, then edit it as you wish
cp .env.example .env

# install vendor directory using composer docker image
docker run --rm --volume "$PWD":/app composer install

# generate Laravel app key
docker run --rm --volume "$PWD":/app composer php artisan key:generate

# fix vendor directory permissions
sudo chown -R 1000:1000 ./vendor

# run the app using Laravel Sail
./vendor/bin/sail up -d
```

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
