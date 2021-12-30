# BAWiM- DVWA
BAWiM course project created by Szymon Bobrowski& Mateusz Świder.
# About
During this classes we're gonna focus on the safety of our session, in particular, how to secure our cookies from various attacks. We will also try to improve our practical skills, utilizing the __'Damn Vulnerable Web Application' (DVWA)__. Should you have any problem, don't hesitate to ask or just go to sources- most likely you can find a solution there.
# Step by step installation
## On Windows
We recommend running the app with xampp:
* download and install xampp (Apache + Mysql + PHP): https://www.apachefriends.org/index.html
* download and unzip DVWA: http://dvwa.co.uk/
* open xampp -> explorer -> htdocs and delete all files, create new folder named dvwa, then move there all downloaded DVWA files
* go to config folder (one of those, that have been moved) and change the name of a main config file `config.inc.php.dist` -> `config.inc.php`
* modify the config file with a notepad or other similar tool and change the default passowrd to blank, like that: `$_DVWA['db_password']='';`
* run the Apache and Mysql servers
* run the web browser- we highly recommend __Firefox__, since some features don't work on other browsers, e.g. chrome
* try to sign in into admin account- the default credentials should be `admin:password`
* at the botton of the page, __Setup / Reset DB tab__ on the left, try to __Create / Reset Database__
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
_To avoid any issues, we suggest you to reset your database and clean all cookies after each of the exercises_
## 1. UPEL quiz
Go to the UPEL website and take the short quiz.
## 2. Weak Session IDs (Brute force)
In this exercise we're gonna consider some bad practices regarding cookies generation, using DVWA. In the __DVWA Security__ tab, you can change the security level of your cookies generator. Then, in the __Weak Session IDs__ tab, you can generate new cookies. Your task is to make out how the cookies are created on the following levels: low, medium, high. In case you need some help- go to the _Viev source_- it's written explicitely in the code. As a report, hand a screenshot of a few cracked cookies hashes on the high level. For cracking, you can use the following site: https://crackstation.net/ (it's possible to crack several hashes at once).  
Now it's clear, that such ways od cookies generation are easy to guess and vulnerable to brute force attacks.
## 3. Cross site scripting (stored)
At first, change the security to low. Now, try to inject a piece of javascript code, that would send the visitor cookies at the given address. If you want to, you can use burp suite or some python script (like http.server <port number>), however it's much easier and less complicated to use some external site, e.g. https://webhook.site/. As a report, pass a snapshot of captured cookies.  
Hint: The default '_Message_' field length is set to _50_- most likely it won't not enough, so just change it in the source code for, let's say, _300_
## 4.
## 5. Last but not least- Session hijacking (Optional)
No matter what the way of seizing somebody's cookies was- now we can make an advatage of it. While logged in on one browser tab, open another one and try to sign in with no credentials given. You can use a cookie manager, like: https://addons.mozilla.org/pl/firefox/addon/cookie-editor/ (for Firefox). The last step is to modify the cookies. Then you need to change your url address source path (remove _/login.php_), so it would look the following way: _<your_ip_address>/<your_dvwa_folder_name>/_. That's it- you should be logged in into hacked user account.  
There is no way to verify the way you've signed in and, hence, there is no need to report that task.


# Sources
https://youtu.be/cak2lQvBRAo  
https://youtu.be/LKE1G4sinBM  
https://youtu.be/xzKEXAdlxPU  
https://youtu.be/UXtxfka2TuY
