FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/vitrage --groups kolla vitrage \
    && mkdir -p /var/lib/vitrage \
    && chown -R 42459:42459 /var/lib/vitrage




ADD vitrage-base-archive /vitrage-base-source
RUN ln -s vitrage-base-source/* vitrage \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /vitrage \
    && mkdir -p /etc/vitrage \
    && cp -r /vitrage/etc/vitrage/* /etc/vitrage/ \
    && chown -R vitrage: /etc/vitrage



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 755 /usr/local/bin/kolla_extend_start

