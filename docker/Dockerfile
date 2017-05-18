FROM amazonlinux:latest

MAINTAINER afym

RUN yum install -y git curl telnet\
    nginx php70-fpm.x86_64 \
    ImageMagick.x86_64 \
    php70.x86_64 \
    php70-bcmath.x86_64 \
    php70-gd.x86_64 \
    php70-imap.x86_64 \
    php70-intl.x86_64 \
    php70-ldap.x86_64 \
    php70-mbstring.x86_64 \
    php70-mcrypt.x86_64 \
    php70-mysqlnd.x86_64 \
    php70-pdo.x86_64 \
    php70-pgsql.x86_64 \
    php70-soap.x86_64 \
    php70-tidy.x86_64 \
    php70-zip.x86_64 \
    php70-pecl-redis.x86_64 \
    php70-pecl-memcache.x86_64 php70-pecl-memcached.x86_64 \
    nginx

RUN mkdir /etc/nginx/sites.d/ -p
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

WORKDIR /usr/share/nginx/html

COPY ./bash/entrypoint.sh /root/entrypoint.sh
COPY ./nginx/conf.d/nginx.conf /etc/nginx/nginx.conf

RUN chmod +x /root/entrypoint.sh

ENTRYPOINT ["/root/entrypoint.sh"]

EXPOSE 80
