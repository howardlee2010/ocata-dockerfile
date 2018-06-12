FROM tor2/centos-source-keystone-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)



ADD plugins-archive /
COPY keystone_bootstrap.sh /usr/local/bin/kolla_keystone_bootstrap
COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_keystone_bootstrap \
    && if [ "$(ls /plugins)" ]; then \
           pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /plugins/*; \
       fi


