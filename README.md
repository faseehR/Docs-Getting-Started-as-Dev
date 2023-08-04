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
Back in your web browser, reload the page. You should now have Odoo’s database configuration page open via a secure https:// connection. Now you can enter usernames and passwords safely to complete the installation process.
links:
https://www.digitalocean.com/community/tutorials/how-to-install-odoo-on-ubuntu-20-04-with-docker
---------------------------------------------------------------------------------------------------------------------------------------------------------
