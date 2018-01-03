FROM shamanzpua/apache2

RUN  apt-get update && apt-get install -y \
  libssl-dev \
  && a2enmod rewrite \
  && pecl install mongodb \
  && docker-php-ext-enable mongodb

ARG USER
RUN useradd -G www-data -m $USER

RUN docker-php-ext-install pcntl

WORKDIR /var/www/html/

# Start apache
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
