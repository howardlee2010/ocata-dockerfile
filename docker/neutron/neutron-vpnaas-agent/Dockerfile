FROM tor2/centos-source-neutron-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







   
       
   

RUN yum -y install openswan && yum clean all

ADD neutron-vpnaas-agent-archive /neutron-vpnaas-agent-source
RUN ln -s neutron-vpnaas-agent-source/* neutron_vpnaas \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /neutron_vpnaas \
    && cp /neutron_vpnaas/etc/neutron/rootwrap.d/* /etc/neutron/rootwrap.d



COPY extend_start.sh /usr/local/bin/kolla_neutron_extend_start
RUN chmod 755 /usr/local/bin/kolla_neutron_extend_start




# TODO(pbourke): The libreswan driver required by redhat derived bases
# currently requires root in Neutron. Remove this if condition once
# https://bugs.launchpad.net/neutron/+bug/1644517 is addressed.
