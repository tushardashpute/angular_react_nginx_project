# Angular 12 + Node.js Express + MySQL example + Nginx : CRUD Application
angular_react_nginx_project

1. Install Nginx on Ubuntu instance:
2. Install nodejs and angular 
3. Install Express/MySQL/sequelize cors 
        
Now you can install:
$ sudo yum clean metadata
$ sudo yum -y install nginx


   apt-get update
   sudo apt-get install -y npm 
   apt-get install -y curl
   curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - 
   sudo apt-get install -y nodejs 
   sudo npm install -g @angular/cli 
   which ng
   sudo apt-get install -y git 
   sudo apt-get install -y nginx 
     
   # nginx -v
      nginx version: nginx/1.18.0 (Ubuntu)
   # node -v
       v12.22.11
   # npm -v
       6.14.16
   # service nginx start
   # service nginx status
   
Now you can check the nginx page at http://public_ip_of_EC2Instance

Now we can copy the Angular12 
  cd /etc/nginx/sites-available
   
   
   
     ng build --prod
     node -v
     npm -v
     ng -v
     ng build --prod
     
   git clone https://github.com/bezkoder/angular-12-node-js-project.git


cd angular-12-node-js-project/
ll
cd angular-12-client/
ll
ng build
ng install
npm install
ng build

cd angular-12-client/
   93  ll
ng serve --port 8081
ng build
ls -ltr
cd static
   
   cd static
  109  ll
  110  cp *  /var/www/html/angular
  111  mkdir -p  /var/www/html/angular
  112  cp *  /var/www/html/angular

 147  vi nginx.conf 
  148  cd sites-
  149  cd sites-available/
  150  ll
  151  vi default 
  152  service nginx restart
  153  cd ..
  154  cd /var/www/html/angular/
  155  ll
  156  cd /opt
  157  ll
  158  cd angular-12-node-js-project/
  159  ll
  160  cd angular-12-client/
