# angular_react_nginx_project
angular_react_nginx_project

1. Install nginx on EC2 instance:

# sudo amazon-linux-extras list | grep nginx
 38  nginx1                   available    [ =stable ]

#  sudo amazon-linux-extras enable nginx1
 38  nginx1=latest            enabled      [ =stable ]

# sudo amazon-linux-extras list | grep nginx
 38  nginx1=latest            enabled      [ =stable ]


        
Now you can install:
$ sudo yum clean metadata
$ sudo yum -y install nginx

# nginx -v
nginx version: nginx/1.20.0

sudo apt-get install -y npm 
    3  apt-get install -y curl
    4  apt-get update
    5  sudo apt-get install -y npm 
    6  apt-get install -y curl
    7  curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash - 
    8  curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - 
    9  sudo apt-get install -y nodejs 
   10  sudo npm install -g @angular/cli 
   11  which ng
   12  sudo apt-get install -y git 
   13  sudo apt-get install -y nginx 
   14  cd /etc/nginx/sites-available
   
   ng build --prod
   26  node -v
   27  npm -v
   28  ng -v
   29  ng build --prod
   git clone https://github.com/bezkoder/angular-12-node-js-project.git
   37  cd angular-12-node-js-project/
   38  ll
   39  cd angular-12-client/
   40  ll
   41  ng build
   42  ng install
   43  npm install
   44  ng build

cd angular-12-client/
   93  ll
   94  ng serve --port 8081
   95  ng build
   96  ls -ltr
   97  cd static
   
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
