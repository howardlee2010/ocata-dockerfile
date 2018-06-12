FROM tor2/centos-source-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







RUN yum -y install jq ceph-common ipmitool && yum clean all

RUN curl -o /usr/bin/kubectl http://storage.googleapis.com/kubernetes-release/release/v1.4.0/bin/linux/amd64/kubectl \
    && chmod 755 /usr/bin/kubectl


