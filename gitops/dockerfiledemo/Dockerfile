from alpine
MAINTAINER Heshan <heshan947102@gmail.com>

# Add repo file
ADD ./README.txt /README.txt

# Install cool software
RUN apk add bash nmap &&\
  touch /tmp/testfile

ENTRYPOINT ["/usr/bin/nmap"]
CMD ["-sn", "172.17.0.0/24"]

