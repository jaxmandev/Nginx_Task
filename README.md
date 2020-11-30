# Nginx Reverse Proxy

## Introduction

APP is currently running on port 3000
- See previous our multi vagrant machine.
Note that browsers use port 80 by default to load web apps

- Set up a reverse proxy.

## Pre-Requisites
* Vagrant
* Virtual Box
* Git

## Tasks

- How to install and configure Nginx as a reverse proxy. 
- Objective is to listen for requests on port 80 and pass them on to port 3000.

## Requisites
- Localhost set to development.local
- Port 80 has App running (Sparta logo should be visible)

## Instructions
1. Run the following
```
vagrant up app
vagrant up db
```

2. Browse to   
http://development.local

3. Visit the fibonacci generator at http://development.local/fibonacci/3
4. The posts page will need some added commands:

```
# login to vagrant
vagrant ssh
# create an environment variable for DB_HOST
echo "DB_HOST='192.168.10.2'" >> ~/.bashrc
# reload the bash terminal
bash
# navigate to app location
cd /home/ubuntu/app/
# stop the app
pm2 stop app.js
# export DB_HOST
export DB_HOST
# start the app again
pm2 start app.js --update-env
```
5. Visit the page at http://development.local/posts

