FROM centos:7
MAINTAINER Heshan <heshan947102@gmail.com>

# Add repo file
ADD ./sander.repo /etc/yum.repos.d/

# Install cool software
RUN yum --assumeyes update && \
yum --assumeyes install bash nmap iproute && \
yum clean all

ENTRYPOINT ["/usr/bin/nmap"]
CMD ["-sn", "172.17.0.0/24"] 
