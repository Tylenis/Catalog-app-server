# Catalog app server

the Item-Catalog-App deployed on Linux server (Amazon Lightsail) using Apache and PostgreSQL.

## IP address

```bash

52.59.250.248
```

## SSH port

```bash
2200
```

## URL to Items-Catalog-App.

[Catalog-App](http://52.59.250.248.nip.io)

```bash

http://52.59.250.248.nip.io
```

## Software installed:
* apache2;
* libapache2-mod-wsgi;
* postgresql;
* python-pip;
* virtualenv;
* psycopg2;
* Item-Catalog-App (includes all required python packages);

## Configuration:
* changed the SSH port from 22 to 2200 (/etc/ssh/sshd_config);
* configured the Lightsail firewall to allow it;
* configured the UFW to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123);
* created a new user account named "grader", gave "grader" the permission to sudo (/etc/sudoers.d/grader); 
* installed a ssh key for "grader";
* configured Apache to serve a Python mod_wsgi application (/var/www/Item-Catalog-App/catalogApp.wsgi, /etc/apache2/sites-available/catalogApp.conf);
* configured Apache to allow "Authorization" headers in requests (required by the Catalog App API).
* updated Authorized JavaScript origins and Authorized redirect URIs in Google Developers Console;
* due to Google restrictions for javascript origins and redirect URIs, used http://nip.io DNS service;

## Third-party resources:
* http://modwsgi.readthedocs.io/en/develop/index.html;
* http://httpd.apache.org/docs;
* http://flask.pocoo.org/docs/1.0/;
* https://help.ubuntu.com/community/PostgreSQL;
* http://www.patricksoftwareblog.com/database-using-postgresql-and-sqlalchemy;
* https://stackoverflow.com/questions/36020374/google-permission-denied-to-generate-login-hint-for-target-domain-not-on-localh;
* https://www.digitalocean.com/community/tutorials/how-to-configure-the-apache-web-server-on-an-ubuntu-or-debian-vps;
* Book: Gareth Dwyer "Flask By Example";
