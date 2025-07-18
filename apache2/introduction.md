# Introduction & Installation
Apache2 (Apache HTTP Server) is an open-source, cross-platform web server software maintained by the Apache Software Foundation. 
It is one of the most widely used web servers globally, known for its stability, flexibility, and extensive module support.

# Basic comments
## To install
First update the system before installing

``sudo apt update``

``sudo apt install apache2``

## To start & Enable

``sudo systemctl start apache2``

``sudo systemctl enable apache2``

## To check status

``sudo systemctl status apache2``

if running below shown
> ● apache2.service - The Apache HTTP Server
   Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
   Active: active (running) since ...

## To Verify Installation

1. Open a web browser.
2. Go to http://localhost or http://your-server-ip.
3. You should see the Apache2 Ubuntu Default Page.





