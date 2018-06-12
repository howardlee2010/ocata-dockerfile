FROM tor2/centos-source-ceph-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)



COPY fetch_ceph_keys.py /usr/bin/

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start /usr/bin/fetch_ceph_keys.py


