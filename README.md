# BAWiM
BAWiM course project
# About
During this classes we're gonna focus on the safety of our session, in particular, how to secure our cookies from various attacks. We'll also try to improve our practical skills, utilizing the 'Damn Vulnerable Web Application' (DVWA).
# Step by step installation
## On Windows
We recommend running the app with xampp:
* download and install xampp (Apache + Mysql + PHP): https://www.apachefriends.org/index.html
* download and unzip DVWA: http://dvwa.co.uk/
* open xampp -> explorer -> htdocs and delete all files, create new folder named dvwa, then move there all downloaded DVWA files
* go to config folder (one of those, that have been moved) and change the name of a main config file `config.inc.php.dist` -> `config.inc.php`
* modify the config file with a notepad or other similar tool and change the default passowrd to blank, like that: `$_DVWA['db_password'] = '';`
* run the Apache and Mysql servers
* run the web browser- we highly recommend __firefox__, since some features don't work on other browsers, e.g. chrome
* try to sign in into admin account- the default credentials should be `admin:password`
* at the botton of the page, setup / reset db tab on the left, try to __Create / Reset Database__
* if you didn't receive any error message, you can skip all the next steps and go to the exercises
* if so, stop Apache and Mysql servers
* go to Mysql -> config -> my.ini
* add the following line `skip-grant-tables` right under `[mysqld]`, it should look like that:
```
(...)
# The MySQL server
default-character-set=utf8mb4
[mysqld]
skip-grant-tables
port=3306
(...)
```
* run Apache and Mysql servers again and repeat previous steps, now you should be able to setup your database and start exercises.

## On Linux

# Exercises

# Sources
https://youtu.be/cak2lQvBRAo  
https://youtu.be/LKE1G4sinBM
