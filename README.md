A sample Docker workflow with Nginx, Node.js and Redis
==================
This repo is based on Fedora Cloud (https://hub.docker.com/r/fedora) and ANAND MANI SANKAR works

What's used: 
* NodeJS: https://github.com/jurikolo/Docker-ex1/tree/master/nodejs
* Nginx: https://github.com/jurikolo/Docker-ex1/tree/master/nginx
* Redis: https://github.com/jurikolo/Docker-ex1/tree/master/redis

How to build:
* NodeJS: docker build --rm -t jurikolo/fedoranodejs .
* Nginx: docker build --rm -t jurikolo/fedoranginx .
* Redis: docker build --rm -t jurikolo/fedoraredis .

How to run (follow exactly this sequence):
* Redis: docker run -d --name redis -p 6379:6379 jurikolo/fedoraredis
* NodeJS1: docker run -d --name node1 -p 8080 --link redis:redis jurikolo/fedoranodejs
* NodeJS2: docker run -d --name node2 -p 8080 --link redis:redis jurikolo/fedoranodejs
* NodeJS3: docker run -d --name node3 -p 8080 --link redis:redis jurikolo/fedoranodejs
* Nginx: docker run -d --name nginx -p 80:80 --link node1:node1 --link node2:node2 --link node3:node3 jurikolo/fedoranginx
