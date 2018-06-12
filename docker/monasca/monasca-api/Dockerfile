FROM tor2/centos-source-monasca-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







ADD monasca-api-archive /monasca-api-source
RUN ln -s monasca-api-source/* monasca-api \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /monasca-api







USER monasca
