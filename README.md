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

 - At the end configuration.php is shown, you need to manually upload that using FTP and delete the installation folder  
