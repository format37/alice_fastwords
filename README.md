## Yandex dialogs alice skill: repeat patter
Framework apps list:  
https://dialogs.yandex.ru/store

### VPS cloud yandex
Get an vps with dialogs image  
https://yandex.ru/dev/dialogs/alice/doc/deploy-ycloud-docpage/

### SSL
If you feel stuck with SSL, just buy SSL and install them with the guide below:  
https://www.reg.ru/support/ssl-sertifikaty/ustanovka-ssl-sertifikata/ustanovka-ssl-sertifikata-na-nginx

### Installation
```sudo su
su -
source /srv/alice-buy-elephant/alice/bin/activate
python3 -m pip install PyMySQL
apt-get update --fix-missing
apt install mysql-client-core-5.7
apt install mariadb-client-core-10.1
sudo apt install mysql-server

systemctl start mysql
mysql
create database fastwords;
use fastwords;

create table users(id int not null auto_increment,user varchar(128) not null,name varchar(36) not null, menu_id int, primary key(id));
alter table users convert to character set utf8mb4 collate utf8mb4_unicode_ci;

create table words(id int not null auto_increment,word varchar(1024) not null,primary key(id));
alter table words convert to character set utf8mb4 collate utf8mb4_unicode_ci;

create table scores(id int not null auto_increment,user varchar(128) not null, word_id int, score int, event_date DATETIME, primary key(id));

create table log(id int not null auto_increment,user varchar(128), menu int, text_in varchar(1024), text_out varchar(1024), event_date DATETIME, primary key(id));
alter table log convert to character set utf8mb4 collate utf8mb4_unicode_ci;

exit

pip install pandas```  

### Result
![result](./images/photo_2020-02-19_22-50-40.jpg)
