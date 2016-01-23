FROM ubuntu:latest

MAINTAINER Kailash Verma <kailashv@cybage.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -qq && apt-get install -y mysql-server-5.5

ADD my.cnf /etc/mysql/conf.d/my.cnf

RUN chmod 664 /etc/mysql/conf.d/my.cnf

ADD run.sh /usr/local/bin/run

ADD rms_o.sql rms.sql

RUN chmod +x /usr/local/bin/run

VOLUME ["/var/lib/mysql"]

EXPOSE 3306

CMD ["/usr/local/bin/run"]
