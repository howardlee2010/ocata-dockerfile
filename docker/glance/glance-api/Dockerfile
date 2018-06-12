FROM tor2/centos-source-glance-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)






    


RUN yum -y install qemu-img && yum clean all

COPY extend_start.sh /usr/local/bin/kolla_glance_extend_start
RUN chmod 755 /usr/local/bin/kolla_glance_extend_start




USER glance