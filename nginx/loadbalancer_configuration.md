## load balancer Configuration
### Install the nginx
```cmd
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```
### Configure custom vhost file

```sh
# sudo nano /etc/nginx/sites-available/load_balancer.conf


## add the confinguration in default configuration file

# # /etc/nginx/nginx.conf

add thus to the http block
upstream backend_servers {
        server app1.radianterp.in;
        server app3.radianterp.in;
    }
##add this conf.d for load balance conf
# /etc/nginx/conf.d/load_balancer.conf

erver {
    listen 80;
    server_name lb.radianterp.in;

    location / {
        proxy_pass http://backend_servers;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

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
lb.radianterp.in

# result is 
![image1](https://github.com/user-attachments/assets/4e1c8eea-1dd3-4b60-ab6b-1bc42234eec1)

refresh the same

![image2](https://github.com/user-attachments/assets/6302b94c-d413-4c2e-a8a7-675e89597046)

