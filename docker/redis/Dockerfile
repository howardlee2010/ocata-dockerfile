FROM tor2/centos-source-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







RUN usermod --append --home /run/redis --groups kolla redis \
    && mkdir -p /run/redis \
    && chown -R 42460:42460 /run/redis



    

RUN yum -y install redis && yum clean all




USER redis