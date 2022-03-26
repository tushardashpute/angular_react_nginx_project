# Angular 12 + Node.js Express + MySQL + Nginx example: CRUD Application
angular_react_nginx_project

1. Install Nginx on Ubuntu instance:
2. Install nodejs and angular 
3. Install Express/MySQL/sequelize cors 
4. Clone the Angular project and run it:
        

**1.  Install Nginx on Ubuntu instance:**
   apt-get update
   
   sudo apt-get install -y nginx 
     
   nginx -v
      nginx version: nginx/1.18.0 (Ubuntu)

   # service nginx start
   # service nginx status
   
Now you can check the nginx page at http://public_ip_of_EC2Instance

**2.  Install nodejs and angular **

           sudo apt-get install -y npm 
           apt-get install -y curl
           curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - 
           sudo apt-get install -y nodejs 
           sudo npm install -g @angular/cli 
           npm install express sequelize mysql2 cors --save
           which ng

   # node -v
       v12.22.11
   # npm -v
       6.14.16
       

**3. Install MySQL DB **

        sudo apt install mysql-server
        sudo service mysql status
        sudo mysql_secure_installation
        sudo service mysql restart

        Login to MySQL DB and create test user, create testDB .
        # mysql

        mysql> CREATE USER 'test'@'localhost'  IDENTIFIED BY '123456';
        Query OK, 0 rows affected (0.01 sec)

        mysql> GRANT ALL PRIVILEGES ON *.* to 'test'@'localhost' WITH GRANT OPTION;
        Query OK, 0 rows affected (0.00 sec)

        mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;l
        +------------------+------------------------------------------------------------------------+-----------------------+-----------+
        | user             | authentication_string                                                  | plugin                | host      |
        +------------------+------------------------------------------------------------------------+-----------------------+-----------+
        | debian-sys-maint | $A$005$}8%^J]Yn_,1wXSH8/tryujIcKjU.xXYmNaI7WLGBiFeAzAHCbyjZYUZ58 | caching_sha2_password | localhost |
        | mysql.infoschema | $A$005$THISISACOMBINATIONOFINVALIDSALTANDPASSWORDTHATMUSTNEVERBRBEUSED | caching_sha2_password | localhost |
        | mysql.session    | $A$005$THISISACOMBINATIONOFINVALIDSALTANDPASSWORDTHATMUSTNEVERBRBEUSED | caching_sha2_password | localhost |
        | mysql.sys        | $A$005$THISISACOMBINATIONOFINVALIDSALTANDPASSWORDTHATMUSTNEVERBRBEUSED | caching_sha2_password | localhost |
        | root             |                                                                        | auth_socket           | localhost |
        | test             | $A$005$8thR 2i]@jp3z,S>521mk5Fa3HUUWipe6RypPVuT7yLROHkdrizzD0wKFy63 | caching_sha2_password | localhost |
        +------------------+------------------------------------------------------------------------+-----------------------+-----------+
        6 rows in set (0.00 sec)

        # mysql -u test -p 123456

        mysql> show databases;
        +--------------------+
        | Database           |
        +--------------------+
        | information_schema |
        | mysql              |
        | performance_schema |
        | sys                |
        +--------------------+
        4 rows in set (0.00 sec)

        mysql> create database testdb;
        Query OK, 1 row affected (0.01 sec)

        mysql> show databases;
        +--------------------+
        | Database           |
        +--------------------+
        | information_schema |
        | mysql              |
        | performance_schema |
        | sys                |
        | testdb             |
        +--------------------+
        5 rows in set (0.00 sec)

4. Clone the Angular project and run it:

        sudo apt-get install -y git 
        cd /opt
        git clone https://github.com/tushardashpute/angular-12-node-js-project.git

        cd angular-12-node-js-project/
        cd node-js-server/

        root@ip-172-31-2-248:/opt/angular-12-node-js-project/node-js-server# npm install express sequelize mysql2 cors --save


        root@ip-172-31-2-248:/opt/angular-12-node-js-project/node-js-server# node server.js 
        (node:21107) [SEQUELIZE0004] DeprecationWarning: A boolean value was passed to options.operatorsAliases. This is a no-op with v5 and should be removed.
        Server is running on port 8080.
        Executing (default): CREATE TABLE IF NOT EXISTS `tutorials` (`id` INTEGER NOT NULL auto_increment , `title` VARCHAR(255), `description` VARCHAR(255), `published` TINYINT(1), `createdAt` DATETIME NOT NULL, `updatedAt` DATETIME NOT NULL, PRIMARY KEY (`id`)) ENGINE=InnoDB;
        Executing (default): SHOW INDEX FROM `tutorials`

        Now we have started serverjs and its running on http://localhost:8080 . It will create tutorials table under the testdb. This table will be used when we will add/update/delete any tutorial 



cd ../angular-12-client/
root@ip-172-31-2-248:/opt/angular-12-node-js-project/angular-12-client# npm install
root@ip-172-31-2-248:/opt/angular-12-node-js-project/angular-12-client# ng build --prod


   
Now we can copy the Angular12 static code generated in static folder to /var/www/html/angular, and update it to nginx sites_vaialbe.

mkdir -p  /var/www/html/angular
root@ip-172-31-2-248:/opt/angular-12-node-js-project/angular-12-client/static# cp * /var/www/html/angular
   
 cd /etc/nginx/sites-available
   
 vi default 
 update the "root /var/www/*;" path to "root /var/www/html/angular;"
   
Now reload the nginx config and restart it.

# service nginx reload
# service nginx restart

Now goto http://localhost --> and access the Angular CRUD app:

<img width="1265" alt="image" src="https://user-images.githubusercontent.com/74225291/160227086-844e1ad3-3fa0-43b7-a845-2c6b086dd5b6.png">

  159  ll
