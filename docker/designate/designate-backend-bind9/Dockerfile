FROM tor2/centos-source-designate-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)






   

RUN yum -y install bind && yum clean all





RUN mkdir -p /var/lib/kolla/ /var/lib/named/ /run/named \
     && chown -R root: /var/lib/named /run/named \
     && chmod 755 /run/named \


