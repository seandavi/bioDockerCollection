############################################################
# Dockerfile to build lofreq variant caller container
# Based on Ubuntu
#
# lofreq is on the path
#
# usage:
#   docker run seandavi/scallop scallop ....
#
############################################################

# Set the base image to Ubuntu
FROM ubuntu

# File Author / Maintainer
MAINTAINER Sean Davis <seandavi@gmail.com>

# Update the repository sources list
RUN apt-get update --fix-missing
RUN apt-get install -y wget python bzip2
RUN apt-get install -y sysstat 
RUN apt-get install -y libboost-all-dev
RUN apt-get install -y coinor-clp
RUN apt-get install -y g++

RUN echo 'ENABLED="true"' > /etc/default/sysstat
RUN echo "PATH=/usr/lib/sysstat:/usr/sbin:/usr/sbin:/usr/bin:/sbin:/bin" > /etc/cron.d/sysstat
RUN echo "* * * * * root command -v debian-sa1 > /dev/null && debian-sa1 1 1\n" >> /etc/cron.d/sysstat


RUN mkdir -p /opt/
WORKDIR /opt/

RUN wget https://github.com/Kingsford-Group/scallop/releases/download/v0.9.8/scallop-0.9.8_linux_x86_64.tar.gz
RUN tar -xvzf scallop-0.9.8_linux_x86_64.tar.gz

RUN ln -s /opt/scallop-0.9.8_linux_x86_64/scallop /usr/bin/scallop

