### Joomla 4 FTP Test


 - Clone repo
 - run `docker-compose up`
 - Open FTP Client and FTP to SERVER `127.0.0.1` USERNAME `www-ftp` PASSWORD `www-ftp`
 
 - go through Joomla 3 installation
   - mysql serrver: mysql
   - mysql username: root
   - mysql password: example

   - ftp host: localhost or 127.0.0.1
   - ftp username: www-ftp
   - ftp password: www-ftp
   - Enable FTP Layer = yes
   - Save FTP Credentials = yes

 - At the end configuration.php is shown, you need to `docker exec -it CONTAINERHASH bash` into the container and use `nano configuration.php` to save the configuration php code. (get the CONTAINERHASH by running command `docker ps` and the hash is the first column called CONTAINER ID, next to `joomla-ftptest_joomla`)

 - while in the container manually delete installation with `rm -Rf installation`

 - while in the container set the permissions of your file `chown www-ftp:www:ftp configuration.php`

 - FIX the ftp path in configuration.php, it should be (and should be found by installer and is not) `/var/www/html`
