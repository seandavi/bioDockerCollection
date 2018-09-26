############################################################
# Dockerfile to build lofreq variant caller container
# Based on Ubuntu
#
# lofreq is on the path
#
# usage:
#   docker run seandavi/lofreq lofreq ....
#
############################################################

# Set the base image to Ubuntu
FROM ubuntu

# File Author / Maintainer
MAINTAINER Sean Davis <seandavi@gmail.com>

# Update the repository sources list
RUN apt-get update --fix-missing
RUN apt-get install -y wget python bzip2 

RUN mkdir -p /opt/
WORKDIR /opt/

# 
RUN wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/2.9.2/sratoolkit.2.9.2-ubuntu64.tar.gz
RUN tar -xvzf sratoolkit.2.9.2-ubuntu64.tar.gz

ENV PATH="/opt/sratoolkit.2.9.2-ubuntu64/bin:${PATH}"

CMD ["/bin/bash", "-h"]
