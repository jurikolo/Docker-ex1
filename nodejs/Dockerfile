FROM fedora
MAINTAINER Jurijs Kolomijecs

RUN dnf -y update && dnf clean all
RUN dnf clean packages
RUN dnf -y install npm make && dnf clean all

ADD . /src

RUN cd /src; npm install; npm install redis

EXPOSE 8080

CMD ["node", "/src/index.js"]
