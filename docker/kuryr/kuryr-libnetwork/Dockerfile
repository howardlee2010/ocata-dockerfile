FROM tor2/centos-source-kuryr-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)





ADD kuryr-libnetwork-archive /kuryr-libnetwork-source
RUN ln -s kuryr-libnetwork-source/* kuryr-libnetwork \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /kuryr-libnetwork




