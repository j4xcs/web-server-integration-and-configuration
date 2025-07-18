## Reverse Proxy Configuration
### Install the nginx
```cmd
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```
### Configure custom vhost file

```sh
# sudo nano /etc/nginx/sites-available/rinoexam.com

server {
    listen 80;
    server_name rinoexam.com;

    location / {
        proxy_pass https://radianterp.in;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
### Copy the file sites-enabled from sites-available
```cmd
ln -s /etc/nginx/sites-available/rinoexam.com
```
### Restart the service
```cmd
sudo systemctl restart nginx
```

# Validate the nginx vhost file
```
sudo nginx -t
```

# Go to the browser
rinoexam.com

# result is 

<img width="1470" alt="Screenshot 2025-03-26 at 8 44 03 PM" src="https://github.com/user-attachments/assets/309d76b0-d239-4ed9-81f0-850c1ad65d0f" />

