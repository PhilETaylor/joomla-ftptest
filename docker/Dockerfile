FROM joomla


RUN apt update && apt install -y vsftpd nano
RUN echo "write_enable=YES" >> /etc/vsftpd.conf
RUN echo "pasv_max_port=10100" >> /etc/vsftpd.conf
RUN echo "pasv_min_port=10100" >> /etc/vsftpd.conf

RUN useradd -s /bin/bash -d /var/www/html/ -m -G sudo www-ftp
RUN echo "www-ftp:www-ftp"|chpasswd www-ftp
RUN chsh -s /bin/bash www-ftp
RUN usermod -d /var/www/html www-ftp
RUN chown -Rf www-ftp:www-ftp /var/www

COPY entrypointCustom.sh /entrypointCustom.sh
RUN chmod +x /entrypointCustom.sh

ENTRYPOINT ["/entrypointCustom.sh"]
CMD ["apache2-foreground"]