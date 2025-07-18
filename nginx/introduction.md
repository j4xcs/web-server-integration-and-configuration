# Introduction & Installation
Nginx (pronounced "engine-x") is a high-performance, open-source web server and reverse proxy server. 
It is known for its speed, scalability, and efficiency, making it a popular alternative to Apache.

# Basic comments
## To install
First update the system before installing

``sudo apt update``

``sudo apt install nginx``

## To start & Enable

``sudo systemctl start nginx``

``sudo systemctl enable nginx``

## To check status

``sudo systemctl status nginx``

if running below shown
> ●nginx.service - A high performance web server and a reverse proxy server
   Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
   Active: active (running) since Sun 2025-02-23 12:16:25 IST; 7h ago


## To Verify Installation

1. Open a web browser.
2. Go to http://localhost 
3. You should see the inginx welcome Page.
