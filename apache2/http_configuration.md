**HTTP  Configuration**
---

We can create a directory in the default path and modify the ownership and permissions.

```bash

sudo mkdir /var/www/example.com
sudo chmod -R 755 /var/www/example.com

```
Then create html file for website index page

```bash
sudo vim /var/www/example.com/index.html

```


 _sample index file_
 
```bash

<html>
    <head>
        <title>Welcome to example.com!</title>
    </head>
    <body>
        <h1>victor</h1>
    </body>
</html>

```

disable the default configuration file

```bash

sudo a2dissite 000-default.conf

```
create the domain in the name of domain 

```bash

sudo vim /etc/apache2/sites-available/example.com.conf

```

use this conf file

```bash

<VirtualHost *:80>
        ServerAdmin webmaster@example.com
        Servername example.com
        DocumentRoot /var/www/example.com
        
        # Redirect http to https
        RewriteEngine On
        RewriteCond %{HTTPS} off
        RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI}

        ErrorLog ${APACHE_LOG_DIR}/example.com.error.log
        CustomLog ${APACHE_LOG_DIR}/example.com.access.log combined

</VirtualHost>


  

```

Then enable your site, disable the old one, and restart the Apache2 server.

```bash
sudo a2ensite example.com.conf
sudo systemctl reload apache2
```
result is 

<img width="1470" alt="Screenshot 2025-03-30 at 9 08 07 PM" src="https://github.com/user-attachments/assets/02440be7-acb3-4f31-8d09-f613c099385a" />
