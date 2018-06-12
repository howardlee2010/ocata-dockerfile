FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/searchlight --groups kolla searchlight \
    && mkdir -p /var/lib/searchlight \
    && chown -R 42442:42442 /var/lib/searchlight




ADD searchlight-base-archive /searchlight-base-source
RUN ln -s searchlight-base-source/* searchlight \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /searchlight \
    && mkdir -p /etc/searchlight \
    && cp -r /searchlight/etc/* /etc/searchlight \
    && chown -R searchlight: /etc/searchlight



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_searchlight_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_searchlight_extend_start

