FROM tor2/centos-source-monasca-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







ADD monasca-log-api-archive /monasca-log-api-source
RUN ln -s monasca-log-api-source/* monasca-log \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /monasca-log







USER monasca
