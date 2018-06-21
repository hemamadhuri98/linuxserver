# Linux-Server-Configuration
## About This Project
  This is the 6 th project in udacity full stack course.In this project We have to deploy one of our project to an instance using  a Linux server instance called [Amazon Lightsail](https://lightsail.aws.amazon.com/ls/webapp/home/instances)

### My Server Information
Server IP Address 13.127.19.160.xip.io

Hosted Web Application URL [Click Here](http://13.127.19.160.xip.io/)

## Softwares Used:
#### lightsail software
#### PuTTy software
#### Flask frame work
#### Apache2

Grader Password
```
unix
```
grader key
```
-----BEGIN RSA PRIVATE KEY-----
MIIEpQIBAAKCAQEA2+KOr7mbAhCPBn7K367WrUhT5jjWBIPkZ5ITdxvKxIaygWvv
NnTzNVEl/YxGaDAlqh7QbyNPCPArJ+PVKCEVWY6UZcSLq4I5GXAdRh9pDsjbN3/d
Q4pFU3QpQMyIRvdDzzDRIKJi5N4PVoCrgpgEld1R2fdRmykNuwwhZoBKn5alMiE0
T5i1bxBc9ht0kL/ktYXlIpiStwL0DBkQGpxDdL5bQGvCirUhtbNVAoLP07O7EE2q
uVvCWpIbyeFsRuZim8bXJeaXH75KlRDuWSLea0qZPRmVX0LZkHUcWMieqYOF2JO3
68jtTde2CGe9ZdJFr7qq/D9BIP3oWawTyqF+fQIDAQABAoIBAQCE2zj3eB/ueW7R
r96IlK1leeQnoIO/qqlg4uQb/ZDgebp1dG/O6Y7h0iwwLIeGAEFhrsilviHM9sA8
k+6BFqw9tmZ3ru/tKvuxIQqvCd+CbV33BKz+WBdXO0KJwos8xb4U/Bv/qd4zBvEh
hREcERoEKvt/xW1rYLzJHaU4t59fGJnV9lJXS5+lck5WgBhF40/HcElvyHUNbYlI
tQ40VzgMOYCzcLxodc2UwJgFgIWpPGymFVnwBsIOKGGsHevdy3XWsVeyLcvkccRD
eH98sbgbE5qLi+AgrctN+9inMW1Di5zKOFV3W4UaQFqeuyCzIrNcOiPIS2uOFer6
rhEUxS6JAoGBAPRpnvvHUssvWITDDgY3v6WakHM7obSjM+qYmkWjlwWHehmr0i1B
VNKTkNsQpyEkEx7pXEdbursX2IWLsE+J0iIN4u2e7fy6HM1KISd2HDPqnONbjxnJ
54t9CIryYU0iEaujN0mYZcC6IqgTEpjM/gdvbQ229/88XM2AO+vZKFh3AoGBAOZP
QCjnCXLSLQr+98S09h/f6EN/BWvUQRZd2S2g6s+COPZcYljvUVlRjDMTOhA+ehRY
ekBhnrAA4gHKf1AL5DhD4nLYqnDt2ZnO5Q1Bvjbgv/uhccnlgojYCtbdqzyM6I9e
+ayPPyX4pFSZvQ07GpDhZo5fXPsNmERP1LNpxZGrAoGAHbZFVHhLsVWlHiaUKt9W
FeyvSMLkCpCYfBlnD7YuYsawajSADW5WwG6d+nOQza+T/3sA88/L6HiiosFzgofP
msIzZw2eAs4hODedxi1OimUoA1+bCtiHpGZjxnhmqbjNix8BVpoHLKG0GtiOtzKc
Yw0BpdwrU8TjxzuijS5OAEsCgYEA0EsMs/GAUiBULIW8gGNJ1jojTigrNwKYeyoV
qXbH5zTXX7jeGaEX6bgfHHJfKSHYN15t8pxXcMbboNMLodGfbmO3AjeCru/uxXSh
JAQ5jFhoSaQRzY+NJ0Z9RybkH7cw/bngBXjom+bseLcyjCzQMggpQMpuxX/eHqo0
rK8UyFECgYEAx5isaujTn/2BgvQ+wgMY60ZTNzbcr8ipwrx0FH95XNm5LOk7SqcF
rwCV2DYcF0FaZdx84rJlouomImlR5X7lbTTIeT421S9v6MTp3ILpoMZ1YKzbAA/c
YxDeTEyXi7TLeo5nHEX2oKGHXCQReJ8ZmamDuuinw+6OpCwEonICPks=
-----END RSA PRIVATE KEY-----

   ```

### To Connect As a grader:
  Save The Private Key Provided in Your Local Machine and Run the Following Command in Terminal
  ```
  ssh -i pathto/key -p 2200 grader@13.127.19.160
  ```
## how to run:
1. Launch your Virtual Machine
2. Follow the instructions provided to SSH into your server
3. Create a new user  grader
4. Give grader permission to sudo
5. Update all installed packages
6. Change the SSH port from 22 to 2200
7. Configure the Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123)
8. Configure the local timezone to UTC
9. Install and configure Apache to serve a Python mod_wsgi application
10. Install and configure PostgreSQL
11. Do not allow remote connections.
12. Install git and clone  your Catalog App project (from your GitHub repository ) so that it functions correctly when visiting your server’s IP address in a browser.
### Configuring The Linux Server

#### Update all the packages
```
sudo apt-get update
```
```
sudo apt-get upgrade
```

#### Create New User 'grader' :
  ```
  sudo adduser grader
  ```
  New User Will be Added
  ```
  sudo nano /etc/sudoers
  ```
  Below the root user Add this line to grant sudo permission to grader
  ```
  grader  ALL=(ALL:ALL) ALL
  ```
  
  #### Create SSH Key Pair:
   On Your Local Computer Open New Terminal and type following command
   ```
   ssh-keygen
   ```
   It Will Generate Private and Public Keys and Saved To .ssh Folder
   
   Then on your VM change to Newly created user
   ```
   su - grader
   ```
   Now Create a New Directory named .ssh
   ```
   mkdir .ssh
   ```
   Create a New File Named authorized_keys
   ```
   sudo nano .ssh/authorized_keys
   ```
   Go to .ssh Folder and open .pub extension file and copy it
   Paste it in authorized_keys 
   ```
   Give Permissions
   chmod 700 .ssh
   chmod 644 .ssh/authorized_keys
   ```
   Now Restart SSH server using following command
   ```
   service ssh restart
   ```
   
   Now Log into grader using private generated 
   ```
   ssh -i .ssh/id_rsa grader@ipaddress 
   ```
  #### Change Port Number From 22 to 2200
   Go to sshd config file using this command
   ```
   sudo nano /etc/ssh/sshd_config
   ```
   Locate port number and change it from 22 to 2200
   Press CTRL+X and Y to exit
   Restart again the ssh server using this command
   
   ```
   service ssh restart
   ```
   
   >Note: Before logging in add new ssh key with Custom,TCP,Portnum:2200 In Networking Tab In Amazon Lightsail Instance  
   
   After creating You can login using following command
   ```
   ssh -i .ssh/id_rsa -p 2200 grader@ipaddress
   ```
   
  #### Disable SSH login as root
  ```
  sudo nano /etc/ssh/sshd_config
  ```
  ```
  cat sudo nano /etc/ssh/sshd_config | egrep "PermitRootLogin"
  Change the  `PermitRootLogin no`
  ```
  #### Configuring ufw firewall
  ```
  sudo ufw allow 2200/tcp
  ```
  ```
  sudo ufw allow 80/tcp
  ```
  ```
  sudo ufw allow 123/udp
  ```
  ```
  sudo ufw enable
  ```
  It Allows all required ports
  
  Now Type this command to check allowed ports 
  ```
  sudo ufw status
  ```
  
  #### Change the time zone
  Change timezone using following command
  ```
  sudo dpkg-reconfigure tzdata
  ```
  
  Select 'None of the Above' and select UTC
  
  #### Install Apache2 Server
  Go to Terminal and type
  
  ```
  sudo apt-get install apache2
  ```
  
  And Then mod_wsgi
  
  ```
  sudo apt-get install python-setuptools libapache2-mod-wsgi
  ```
  
  Now Enable mod_wsgi
  
  ```
  sudo a2enmod wsgi
  ```
  ##### Setup Your Flask App with Apache2
   Creating a Flask App
   Go to /var/www/ directory
   ```
   cd /var/www/
   ```
   
   Then Create a New Folder Named FlaskApp

     ```
    sudo mkdir FlaskApp
     ```
   
   Now Install Git
   
   ```
   sudo apt-get install git
   ```
   
   Go to the FlaskApp 
   ```
   cd FlaskApp
   ```
   Now Clone Your Repository Here
  
   
   ```
   sudo git clone https://github.com/username/catalog.git
   ```
   
   Rename Your Repository Name as FlaskApp

   
   Then Rename Your project main file to `__init__.py`
   Now Use following code instead of secret_client.json  in the script due to error while accessing json
   ```
   PROJECT_ROOT = os.path.realpath(os.path.dirname(__file__))
   json_url = os.path.join(PROJECT_ROOT, 'client_secrets.json')
   ```

   Reffered from [stack overflow](https://stackoverflow.com/questions/44742566/wsgi-cant-find-file-in-same-directory-in-app)
   
  ##### Install Postgres
   Install Postgres
   ```
   sudo apt-get install postgresql
   ```
   
   Now type

   ```
   sudo su - postgres
   ```

   postgres shell 
   ```
   psql
   ```
   
   create user 
   ```
   CREATE USER catalog WITH PASSWORD 'password';
   ```
   
   Give Permission 
   ```
   ALTER USER catalog CREATEDB;
   ```
   
   Create a Database using name Catalog
   ```
   CREATE DATABASE catalog WITH OWNER catalog;
   ```
   
   connect to Database
   ```
   \c catalog
   ```
   
   Revoke all permissions 
   ```
   REVOKE ALL ON SCHEMA public FROM public;
   ```
   
   Give schema permission to user catalog 
   ```
   GRANT ALL ON SCHEMA public TO catalog;
   ```
   
   exit  
   ```
   \q and exit
   ```
   
   Change the database connection in both `database_setup.py` and `__init__.py` as `engine = create_engine('postgresql://catalog:password@localhost/catalog')`

  #### Enable New Virtual Host
   `sudo nano /etc/apache2/sites-available/FlaskApp.conf`
   
   Paste This code
   ```
   <VirtualHost *:80>
		ServerName yourstaticip.xip.io
		ServerAdmin admin@mywebsite.com
		WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi
		<Directory /var/www/FlaskApp/FlaskApp/>
			Order allow,deny
			Allow from all
		</Directory>
		Alias /static /var/www/FlaskApp/FlaskApp/static
		<Directory /var/www/FlaskApp/FlaskApp/static/>
			Order allow,deny
			Allow from all
		</Directory>
		ErrorLog ${APACHE_LOG_DIR}/error.log
		LogLevel warn
		CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
   ```
   Enable  virtual host 
   `sudo a2ensite FlaskApp`
   
   Disabling Default page
   `sudo a2dissite 000-default.conf`
   
  #### Create .wsgi file
    ```
    cd /var/www/FlaskApp
    sudo nano flaskapp.wsgi 
    ```
   Paste the following code 
   
   ```
   #!/usr/bin/python
    import sys
    import logging
    logging.basicConfig(stream=sys.stderr)
    sys.path.insert(0,"/var/www/FlaskApp/")

    from FlaskApp import app as application
    application.secret_key = 'Add your secret key'
   ```
   save and exit
   
   This one is reffered from [Digital ocean](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
   
   #### Installing requirements

   ` pip install flask sqlalchemy psycopg2 requests oauth2client`
   
   #### Setup google oauth2
   Login to your [developer console](https://console.developers.google.com) and select your project and edit OAuth details as following
   
   Javascript origin url
   `http://yourstaticip.xip.io`
   
   redirect URI
   
   `http://yourstaticip.xip.io\login`
   
   `http://yourstaticip.xip.io\gconnect`
   
   `http://yourstaticip.xip.io\callback`
   
   xip.io is a free DNS which will be the same as using IP address
   
   #### Now
   Restart your apache2

   ```
   sudo service apache2 restart
   ```
   ## Third Party Resources
   [developer console](https://console.developers.google.com)<br>
   [Digital ocean](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)<br>
   [stack overflow](https://stackoverflow.com/questions/44742566/wsgi-cant-find-file-in-same-directory-in-app)
   
