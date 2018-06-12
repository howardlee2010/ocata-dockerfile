FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/zaqar --groups kolla zaqar \
    && mkdir -p /var/lib/zaqar \
    && chown -R 42452:42452 /var/lib/zaqar



ADD zaqar-archive /zaqar-source
RUN ln -s zaqar-source/* zaqar \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt pymongo /zaqar \
    && mkdir -p /etc/zaqar \
    && cp -r /zaqar/etc/* /etc/zaqar/ \
    && mv /etc/zaqar/policy.json.sample /etc/zaqar/policy.json \
    && chown -R zaqar: /etc/zaqar



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start




USER zaqar