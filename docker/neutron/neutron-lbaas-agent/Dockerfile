FROM tor2/centos-source-neutron-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)






RUN yum -y install haproxy net-tools && yum clean all



ADD neutron-lbaas-agent-archive /neutron-lbaas-agent-source
RUN ln -s neutron-lbaas-agent-source/* neutron_lbaas \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /neutron_lbaas \
    && cp /neutron_lbaas/etc/neutron/rootwrap.d/* /etc/neutron/rootwrap.d \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/neutron/rootwrap.conf



COPY extend_start.sh /usr/local/bin/kolla_neutron_extend_start
RUN chmod 755 /usr/local/bin/kolla_neutron_extend_start




USER neutron