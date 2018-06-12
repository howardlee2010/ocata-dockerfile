FROM tor2/centos-source-monasca-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







ADD monasca-persister-archive /monasca-persister-source
RUN ln -s monasca-persister-source/* monasca-persister \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /monasca-persister







USER monasca
