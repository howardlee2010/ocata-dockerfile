FROM tor2/centos-source-openvswitch-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)



COPY ovs_ensure_configured.sh /usr/local/bin/kolla_ensure_openvswitch_configured
COPY extend_start.sh /usr/local/bin/kolla_openvswitch_extend_start
COPY start_ovsdb_server.sh /usr/local/bin/start-ovsdb-server
RUN chmod 755 /usr/local/bin/kolla_ensure_openvswitch_configured \
              /usr/local/bin/kolla_openvswitch_extend_start \
              /usr/local/bin/start-ovsdb-server


