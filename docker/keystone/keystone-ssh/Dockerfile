FROM tor2/centos-source-keystone-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)






    

RUN yum -y install openssh-server rsync && yum clean all

RUN sed -ri 's/session(\s+)required(\s+)pam_loginuid.so/session\1optional\2pam_loginuid.so/' /etc/pam.d/sshd

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start


