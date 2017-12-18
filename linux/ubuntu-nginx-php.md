apt-cache pkgnames | grep php7

For example, if you want to deploy your application based on the LAMP stack, usually, you can install the below packages after installing Apache:
sudo apt-get install -y apache2
sudo apt-get install -y php7.0 libapache2-mod-php7.0 php7.0-cli php7.0-common php7.0-mbstring php7.0-gd php7.0-intl php7.0-xml php7.0-mysql php7.0-mcrypt php7.0-zip

Alternatively, if you want to deploy your application based on the LEMP stack, you can install the following packages after installing Nginx:
sudo apt-get install -y nginx
sudo apt-get install -y php7.0 php7.0-fpm php7.0-cli php7.0-common php7.0-mbstring php7.0-gd php7.0-intl php7.0-xml php7.0-mysql php7.0-mcrypt php7.0-zip

php -v

The main config file of PHP 7.0 will be saved as /etc/php/7.0/apache2/php.ini (Apache) or /etc/php/7.0/fpm/php.ini (Nginx). You can use the vi text editor to modify relevant settings in that file.

sudo vi /etc/php/7.0/apache2/php.ini
or
sudo vi /etc/php/7.0/fpm/php.ini

Remember to restart Apache or Nginx if you make any changes to that file or any other PHP config files:
sudo systemctl restart apache2.service
or
sudo systemctl restart nginx.service php7.0-fpm.service
