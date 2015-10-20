dockerfiles-fedora-redis
========================

Fedora dockerfile for redis

To build:

Copy the sources down -

	# docker build --rm -t jurikolo/fedoraredis .

To run:

	# docker run -d -p 6379:6379 jurikolo/fedoraredis

To test:

	# nc localhost 6379

