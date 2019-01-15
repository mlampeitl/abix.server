FROM postgres
MAINTAINER Michael Lampeitl <michael.lampeitl@alientec.net>

#
# Installing Software
# vim, ip
RUN set -eux; \
	apt-get update; \
	apt-get upgrade -y; \
	apt-get install -y vim iproute2

#
# Create OS user abix
RUN set -eux; \
	groupadd --gid=1701 abix; \
	useradd --uid=1701 --gid=1701 --create-home --system abix

#
# Default DB Name
ENV POSTGRES_DB docker_tmp

#Copy the DB creation script to image
COPY create_db.sql /docker-entrypoint-initdb.d
