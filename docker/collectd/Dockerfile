FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/collectd --groups kolla collectd \
    && mkdir -p /var/lib/collectd \
    && chown -R 42409:42409 /var/lib/collectd



RUN yum -y install collectd && yum clean all

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start \
    && chown -R collectd /var/lib/collectd \
    && chown -R collectd /etc/collectd* \
    && chown -R collectd /var/run/




USER collectd