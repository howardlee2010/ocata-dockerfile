FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/solum --groups kolla solum \
    && mkdir -p /var/lib/solum \
    && chown -R 42444:42444 /var/lib/solum




ADD solum-base-archive /solum-base-source
RUN ln -s solum-base-source/* solum \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /solum \
    && mkdir -p /etc/solum \
    && cp -r /solum/etc/solum/* /etc/solum/ \
    && chown -R solum: /etc/solum



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_solum_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_solum_extend_start

