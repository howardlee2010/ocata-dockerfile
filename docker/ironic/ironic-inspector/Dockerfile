FROM tor2/centos-source-ironic-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)






    



ADD ironic-inspector-archive /ironic-inspector-source
RUN ln -s ironic-inspector-source/* ironic-inspector \
    && mv /etc/ironic /etc/ironic-inspector \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /ironic-inspector \
    && cp /ironic-inspector/rootwrap.conf /etc/ironic-inspector/ \
    && cp -r /ironic-inspector/rootwrap.d/ /etc/ironic-inspector/ \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/ironic-inspector/rootwrap.conf

COPY ironic_sudoers_source /etc/sudoers.d/kolla_ironic_inspector_sudoers



COPY extend_start.sh /usr/local/bin/kolla_ironic_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_ironic_inspector_sudoers \
    && chmod 755 /usr/local/bin/kolla_ironic_extend_start




USER ironic