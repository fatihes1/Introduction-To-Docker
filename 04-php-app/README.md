FROM php:7-apache
COPY . /var/www/html/
EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]

## Notlar

- `FROM php:7-apache` komutu ile base image olarak `apache web server` içeren bir `PHP` image'i belirlenir.

- `COPY . /var/www/html/` dizindeki tüm kodların container'ın up olduğu ağda `/var/www/html/` dizinine atılmasını sağlar.

- `EXPOSE 80` ile Docker Hub içerisinde container'ın 80 numaralı portta ayağa kalkması sağlanır.

- `CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]` komutu ile `Apache2 web sunucusu`'nun çalışması sağlanır.

- `docker build -t simple-php-app` ile images build edilir.

- `docker run -p 8080:80 simple-php-app` ile image'in container olarak ayağa kalkması sağlanır. Böylelikle `localhost:8080` üzerinde `index.php` içerisindeki kodun çıktısı bizi karşılar.
