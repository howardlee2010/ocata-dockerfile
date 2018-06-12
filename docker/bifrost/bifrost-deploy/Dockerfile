FROM tor2/centos-source-bifrost-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)



ENV container docker





RUN rm -f $(find /lib/systemd/system/sysinit.target.wants/ ! -name systemd-tmpfiles-setup.service -type l); \
    rm -f /lib/systemd/system/multi-user.target.wants/*; \
    rm -f /etc/systemd/system/*.wants/*; \
    rm -f /lib/systemd/system/local-fs.target.wants/*; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
    rm -f /lib/systemd/system/basic.target.wants/*; \
    rm -f /lib/systemd/system/anaconda.target.wants/*;





RUN yum -y install e2fsprogs && yum clean all

CMD [ "/sbin/init" ]


