FROM tor2/centos-source-neutron-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)





ADD neutron-sfc-agent-archive /neutron-sfc-agent-source
RUN ln -s neutron-sfc-agent-source/* neutron-sfc-agent \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /neutron-sfc-agent



COPY extend_start.sh /usr/local/bin/kolla_neutron_extend_start
RUN chmod 755 /usr/local/bin/kolla_neutron_extend_start




USER neutron