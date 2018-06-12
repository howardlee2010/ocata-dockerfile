FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/cloudkitty --groups kolla cloudkitty \
    && mkdir -p /var/lib/cloudkitty \
    && chown -R 42408:42408 /var/lib/cloudkitty




ADD cloudkitty-base-archive /cloudkitty-base-source
RUN ln -s cloudkitty-base-source/* cloudkitty \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /cloudkitty \
    && mkdir -p /etc/cloudkitty  \
    && cp -r /cloudkitty/etc/cloudkitty/* /etc/cloudkitty/ \
    && chown -R cloudkitty: /etc/cloudkitty



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_cloudkitty_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_cloudkitty_extend_start

