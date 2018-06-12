FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/panko --groups kolla panko \
    && mkdir -p /var/lib/panko \
    && chown -R 42438:42438 /var/lib/panko



    

       
RUN yum -y install httpd mod_wsgi python-ldappool && yum clean all
RUN sed -i -r 's,^(Listen 80),#\1,' /etc/httpd/conf/httpd.conf

    
ADD panko-base-archive /panko-base-source

RUN ln -s panko-base-source/* panko \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /panko \
    && mkdir -p /etc/panko \
    && cp -r /panko/etc/panko/* /etc/panko/ \
    && chown -R panko: /etc/panko



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_panko_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_panko_extend_start

