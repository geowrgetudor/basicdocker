# Basic Docker DEV environment for Web Developers

Lighweight and simple. Do NOT use this in production.

* PHP 7.3
* MySql 8.0
* Nginx
* phpMyAdmin
* Redis
* Composer
* Mailhog

## Installation

Clone or download this repository

```bash
git clone git@github.com:zippos/basicdocker.git
```

## Usage

Copy it's content to your project root directory.

**Note:** If your project's ```index.php``` file isn't in the root directory of your project change the ```nginx.conf``` file accordingly.

Example for Laravel:
```
# default root path
root /application;

# laravel root path
root /application/public;
```

Run
```
docker-compose up -d
```

You can easily stop, remove and rebuild all containers with just one command.
```
./docker-rebuild.sh
```

Exposed ports
```
localhost:8000 # webserver
localhost:8081 # mailhog
localhost:8080 # phpmyadmin
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

#### Soon and .env file to configure everything from above

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)