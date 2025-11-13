FROM php:8.2-apache

# Enable Apache mod_rewrite (optional)
RUN a2enmod rewrite

COPY . /var/www/html

# Fix permissions so Apache can read them
RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

# Add Directory permissions to Apache config
RUN echo '<Directory /var/www/html/>\n\
    Options Indexes FollowSymLinks\n\
    AllowOverride All\n\
    Require all granted\n\
</Directory>' >> /etc/apache2/apache2.conf