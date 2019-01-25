WordPressi allalaadimiseks /var/www/html kausta:

cd /var/www/html/

wget http://wordpress.org/latest.zip

aptitude install unzip - installib utiliidi, mis pakib lahti faile

unzip -q latest.zip

Õiguste Määramine:

chown -R www-data:www-data /var/www/html/wordpress

chmod -R 755 /var/www/html/wordpress

Uplad kausta tegemine

mkdir -p /var/www/html/wordpress/wp-content/uploads

Õiguste andmine, et saaks kirjutada wordpressi kausta

chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads

Mysql seadistamine wordpressi jaoks

mysql -u root -p

CREATE DATABASE wordpress;

CREATE USER user@localhost IDENTIFIED BY 'qwerty';

GRANT ALL PRIVILEGES ON wordpress.* TO user@localhost;

FLUSH PRIVILEGES;
