FROM tor2/centos-source-monasca-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







ADD monasca-notification-archive /monasca-notification-source
RUN ln -s monasca-notification-source/* monasca-notification \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /monasca-notification







USER monasca
