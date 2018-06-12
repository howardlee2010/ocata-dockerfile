FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/heat --groups kolla heat \
    && mkdir -p /var/lib/heat \
    && chown -R 42418:42418 /var/lib/heat




ADD heat-base-archive /heat-base-source
RUN ln -s heat-base-source/* heat \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /heat \
    && mkdir -p /etc/heat \
    && cp -r /heat/etc/heat/* /etc/heat/ \
    && chown -R heat: /etc/heat



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_heat_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_heat_extend_start

