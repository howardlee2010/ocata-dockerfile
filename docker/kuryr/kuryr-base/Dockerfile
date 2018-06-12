FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)





ADD kuryr-base-archive /kuryr-base-source
# NOTE(Jeffrey4l): remove kuryr-lib constraint in upper-constraints.txt file.
# Otherwise, it will be failed.
RUN ln -s kuryr-base-source/* kuryr-base \
    && sed -i 's|^kuryr-lib===.*$||g' requirements/upper-constraints.txt \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /kuryr-base



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start

