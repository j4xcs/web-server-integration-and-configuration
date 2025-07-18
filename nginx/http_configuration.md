## Webserver Configuration for nginx
First, Change for Root User
```bash
vi /etc/nginx/sites-available/ngiexam.com

add this content:
-----------------
server {
    listen       80;
    server_name  ngiexam.com;
    access_log /var/log/nginx/ngiexam.com.access.log;
    error_log  /var/log/nginx/ngiexam.com.error.log;

    location / {
        root   /var/www/ngiexam.com;
        index  index.html index.htm;
    }
}
```

**create directory file**

```bash
mkdir /var/www/ngiexam.com
```

**change the directory**

```bash
cd /etc/nginx/sites-enabled
```
**copy the file sites-enabled from site-available**
```bash
ln -s /etc/nginx/sites-available/ngiexam.com ./
```

**restart the server**

```bash
systemctl restart nginx
```
**status of the server**
```bash
systemctl status nginx
```
**Create index.html file and put the information:**
```bash
vim /var/www/ngiexam.com/index.html

add this content:
-----------------
hi victor
```
**Enter into the ip and domain name in /etc/hosts**
```bash
vim /etc/hosts

# localhost entry
ip address    domain name
192.168.31.31 ngiexam.com

```
**To run inside the terminal**
```bash
curl ngiexam.com
```
**Output**



![image](https://github.com/user-attachments/assets/47fb281a-97cd-471e-9753-2c8061c4a932)

