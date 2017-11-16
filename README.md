# udacity-server-config
Udacity Server Config Project

**Server IP Address: 18.216.138.184**
Visit http://18.216.138.184 to see the deployed application.

Software Installed
------------------
### System Level ###
1) Apache2
2) Postgresql
3) Mod_WSGI
4) Emacs

### Python ###
1) Python virtual environment see [Flask Docs](http://flask.pocoo.org/docs/0.12/installation/)
2) psycopg2
3) Flask
4) SQLAlchemy
5) Google python API and OAuth2 python libraries see [Google Docs at 'Language Specific Requirements'](https://developers.google.com/api-client-library/python/auth/web-app)
6) requests library
7) Item Catalog Project [see](https://github.com/k-antonius/item-catalog-udacity)

Configuration Changed
---------------------
1) Add grader user
  - give sudo access
2) Add public RSA key for grader user
3) edit /etc/ssh/sshd_config to change ssh port to 2200
  - change folder and file permissions
4) update and enable ufw
  - disable all incoming ports except 80, 2200, and 143
  - allow all outgoing requests by default
5) Configure a postgres role "catalog" not a superuser
  - add a ubuntu user of the same name so that it can log into the psql
  - create database catalog
  - update application code for new database name/password/user
  - postgres does not allow remote access by default
6) edit Apache config file `/etc/apache2/sites-available/item-catalog.conf`
7) create .wsgi file that activates the python virtual environment
8) enable mod_wsgi
  

Resources Used 
--------------
*Unless Already Mentioned above*
1) [Digital Ocean Deploy a Flask App](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
2) [Digital Ocean Setup Postgresql](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04)
3) [Flask Deployment to ModWSGI](http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/)
