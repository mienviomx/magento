
Contenedores Docker para el desarrollo de Magento 2.4.x que incluyen:

  - PHP 7.4
  - Apache 2.4
  - MYSQL 8
  - Varnish 6 FPC  
  - RabbitMQ  
  - PhpMyAdmin
  - memcached
  - ELASTIC search 7.x
  - REDIS Session, System, FPC
  - Scaleable php-apache service

## Instalacion

1. git clone https://github.com/gaiterjones/docker-magento2  
2. EDIT .env - **add your Magento authentication keys**  
3. `docker-compose build`
4. `docker-compose up -d`   
5. Instalar sample data
`docker-compose exec -u magento php-apache install-sampledata`

6. Instalar Magento
`docker-compose exec -u magento php-apache install-magento`

7. Desabilitar MFA
`docker-compose exec -u magento php-apache bin/magento module:disable Magento_TwoFactorAuth`

## TEST

 - Admin
http://magento2.dev.com/admin  
 - Frontend
http://magento2.dev.com   
 - CLI


    `docker-compose exec -u magento php-apache bash`


Para solucionar problemas de diseño con datos de demostración : `docker-compose exec -u magento php-apache cp /var/www/dev/magento2/vendor/magento/module-cms-sample-data/fixtures/styles.css /var/www/dev/magento2/pub/media/`
