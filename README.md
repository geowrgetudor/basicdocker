# Basic Docker DEV environment for Web Developers

Lighweight and simple. Do NOT use this in production.

## Upgrade

Note: If you were running this before and want to upgrade from PHP 7.3 to PHP 7.4 you will just need to remove the php-fpm container and rebuild it.

```
docker-compose stop
docker-compose rm <php_fpm_container_id>
docker-compose build --no-cache
docker-compose up -d --force-recreate
```

## Packages

* PHP 7.4
* MySql 8.0
* Nginx
* phpMyAdmin
* Redis
* Composer
* Mailhog

## Installation

Clone or download this repository in your project's root folder

```bash
git clone git@github.com:zippos/basicdocker.git
```

## Usage

Copy ```.env.example``` to ```.env```.
By default the ```HOST_ROOT``` is set to the parent folder but you can set it up however you want.

Run
```
docker-compose up -d
```

**Note:** If your project's ```index.php``` file isn't in the root directory of your project change the ```nginx.conf``` file accordingly.

Example for Laravel:
```
# default root path
root /application;

# laravel root path
root /application/public;
```

You can easily stop, remove and rebuild all containers with just one command.
```
./docker-rebuild.sh
```

**WARNING!** By using ```docker-rebuild.sh``` you will lose all your databases.

Exposed ports
```
localhost:8000 # webserver default
localhost:8081 # mailhog default
localhost:8080 # phpmyadmin default
```

Hostnames
```
mysql # for mysql
redis # for redis
php-fpm # for php-fpm (port 9000)
mailhog # for mail
```

MySql default user & password
```
root:root
```

Upload size limit
```
256M # phpmyadmin
100M # webserver
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)