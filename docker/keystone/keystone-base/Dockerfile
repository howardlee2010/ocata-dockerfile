FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/keystone --groups kolla keystone \
    && mkdir -p /var/lib/keystone \
    && chown -R 42425:42425 /var/lib/keystone



    
        
RUN yum -y install httpd mod_wsgi python-ldappool && yum clean all
RUN sed -i -r 's,^(Listen 80),#\1,' /etc/httpd/conf/httpd.conf

    


#ADD keystone-base-archive /keystone-base-source
RUN mkdir -p /keystone-base-source && git clone https://github.com/openstack/keystone.git -b stable/ocata /keystone-base-source/keystone-base 
RUN ln -s keystone-base-source/* keystone \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /keystone \
    && mkdir -p /etc/keystone /var/www/cgi-bin/keystone \
    && cp -r /keystone/etc/* /etc/keystone/ \
    && cp /var/lib/kolla/venv/bin/keystone-wsgi-admin /var/www/cgi-bin/keystone/admin \
    && cp /var/lib/kolla/venv/bin/keystone-wsgi-public /var/www/cgi-bin/keystone/main \
    && chown -R keystone: /etc/keystone /var/www/cgi-bin/keystone




RUN chown -R keystone: /var/www/cgi-bin/keystone \
    && chmod 755 /var/www/cgi-bin/keystone/*

