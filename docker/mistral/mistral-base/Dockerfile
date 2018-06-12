FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/mistral --groups kolla mistral \
    && mkdir -p /var/lib/mistral \
    && chown -R 42430:42430 /var/lib/mistral




ADD mistral-base-archive /mistral-base-source
RUN ln -s mistral-base-source/* mistral \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install /mistral \
    && mkdir -p /etc/mistral \
    && cp -r /mistral/etc/* /etc/mistral/ \
    && chown -R mistral: /etc/mistral



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_mistral_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_mistral_extend_start