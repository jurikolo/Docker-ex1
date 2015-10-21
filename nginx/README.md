dockerfiles-fedora-nginx
========================

Fedora dockerfile for nginx

To build:

Copy the sources down -

    # docker build --rm -t jurikolo/fedoranginx .

To run:

    # docker run -d -p 80:80 jurikolo/fedoranginx

To test:

    # curl http://localhost

