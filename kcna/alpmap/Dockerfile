from alpine
MAINTAINER Sander <mail@sandervanvugt.nl>

# Add repo file
ADD ./sander.repo /etc/yum.repos.d/

# Install cool software
RUN     apk add bash nmap

CMD ["/usr/bin/nmap", "-sn", "172.17.0.0/24"]

