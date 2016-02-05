contenda
========

running dev
-----------

1) start mysql

using docker. see `docker-compose.yml` for details.
take further look at `wordpress/wp-config.php` if your local settings differ.

watch out, that php connects to mysql using a unix socket if you use "localhost" as database host.
use 127.0.0.1 if you want to use docker or TCP instead of a socket.

    docker-compose up

2) start php

using php built in http-server. use `wordpress` as docroot:

    php -S localhost:8080 -t wordpress

upgrading wordpress
-------------------

using composer:

1) change desired version in composer.json
2) run update:

    composer.phar update

3) update wordpress-database

http://localhost:8080/wp-admin/upgrade.php

or

http://www.contenda.at/wp-admin/upgrade.php