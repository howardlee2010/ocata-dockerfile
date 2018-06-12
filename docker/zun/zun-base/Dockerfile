FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)





ADD zun-base-archive /zun-base-source
RUN ln -s zun-base-source/* zun \
    && useradd --user-group --create-home --home-dir /var/lib/zun zun \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /zun \
    && mkdir -p /etc/zun \
    && cp -r /zun/etc/* /etc/zun/ \
    && chown -R zun: /etc/zun



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN usermod -a -G kolla zun \
    && touch /usr/local/bin/kolla_zun_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_zun_extend_start

