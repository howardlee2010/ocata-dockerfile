FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/tacker --groups kolla tacker \
    && mkdir -p /var/lib/tacker \
    && chown -R 42446:42446 /var/lib/tacker




ADD tacker-archive /tacker-source
RUN ln -s tacker-source/* tacker \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /tacker \
    && mkdir -p /etc/tacker \
    && cp -r /tacker/etc/tacker/* /etc/tacker \
    && chown -R tacker: /etc/tacker



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 755 /usr/local/bin/kolla_extend_start




USER tacker