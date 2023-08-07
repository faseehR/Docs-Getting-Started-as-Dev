# Docs-Getting-Started-as-Dev
Odoo Setup As Local Container:
-----------------------------------------------------------------------------------------------------------------------------------------------------------
Steps:

Ubuntu must be installed in computer

Run following commands on ubuntu

commands to install docker

sudo apt update

sudo apt install docker-compose

docker-compose –version

mkdir ~/odoo

cd ~/odoo

Now open a new blank YAML file called docker-compose.yml using nano or your preferred editor:

nano docker-compose.yml

Lines in uml file

mkdir ~/odoo

cd ~/odoo

Now open a new blank YAML file called docker-compose.yml using nano or your preferred editor:

nano docker-compose.yml

nano .env

Add the following lines into the file, substituting in a POSTGRES_USER and POSTGRES_PASSWORD of your choice in place of the highlighted values:

.env

# postgresql environment variables

POSTGRES_DB=postgres

POSTGRES_PASSWORD=a_strong_password_for_user

POSTGRES_USER=odoo

PGDATA=/var/lib/postgresql/data/pgdata

# odoo environment variables

HOST=postgres

USER=odoo

PASSWORD=a_strong_password_for_user

openssl rand -base64 30

docker-compose up -d

docker-compose stop

curl --head http://localhost:8069

sudo apt update

sudo apt install nginx

sudo ufw allow "Nginx Full"

sudo nano /etc/nginx/sites-available/odoo.conf


sudo ln -s /etc/nginx/sites-available/odoo.conf /etc/nginx/sites-enabled/

Use nginx -t to verify that the configuration file syntax is correct:

sudo nginx -t

sudo systemctl reload nginx.service

sudo apt install certbot python3-certbot-nginx

sudo certbot --nginx -d your_domain_here


Back in your web browser, reload the page. You should now have Odoo’s database configuration page open via a secure https:// connection. Now you can enter 

usernames and passwords safely to complete the installation process.

links:

https://www.digitalocean.com/community/tutorials/how-to-install-odoo-on-ubuntu-20-04-with-docker

youtube link:

https://questradigital.slack.com/archives/C05GVE2125R/p1690872979594189

---------------------------------------------------------------------------------------------------------------------------------------------------------
Task 2:

Odoo setup Local environment

Links for setting up local environment

https://kics.edu.pk/essl/blog/setting-up-odoo/

https://www.youtube.com/watch?v=nVFBajJ-sxE

------------------------------------------------------------------------------------------------------------------------------------------------------------------

Task 3:

Odoo HR module code explanation

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

Task 4:

Custom module creation in Odoo

 First install pycharm in ubuntu to run all the cloned files from odoo repositery and then I added odoo conf file in that folder also.

After that I created a custom folder to make new modules in it.

Then make a custom addons folder in which  create a new folder named as hr_attendence in which  create 4 files these are

1-init.py

2-manifest.py

3-controllers

4-models

Then  create a python file in controllers in where api endpoints are defined using http.route ,here is a basic structure of it.


from odoo import http

from odoo.http import request

class hrattendance():

@‌http.route('/api/attendance/checkin', type='json', auth='user', methods=['POST'])

def checkin(self,id):

return {'message': 'CheckIn successfull'}

@http.route('/api/attendance/checkout', type='json', auth='user', methods=['POST'])

def checkout(self,id):

return {'message': 'Checkout successfull'}
