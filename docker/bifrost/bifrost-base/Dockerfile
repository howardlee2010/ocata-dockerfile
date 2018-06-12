FROM tor2/centos-source-openstack-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)








RUN usermod --append --home /var/lib/bifrost --groups kolla bifrost \
    && mkdir -p /var/lib/bifrost \
    && chown -R 42404:42404 /var/lib/bifrost




ENV VENV /var/lib/kolla/venv

ADD bifrost-base-archive /bifrost-base-source
COPY build_arg.yml /tmp/build_arg.yml
RUN ln -s bifrost-base-source/* bifrost \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt /bifrost

WORKDIR /bifrost




RUN bash -c 'sed -e "s/\-\-force\-reinstall //g" -i /bifrost/playbooks/roles/bifrost-{ironic,keystone}-install/tasks/install.yml' \
    && bash -c './scripts/env-setup.sh && source ./env-vars && \
    ansible-playbook -vvvv -i /bifrost/playbooks/inventory/target /bifrost/playbooks/install.yaml \
    -e @/tmp/build_arg.yml && \

    yum clean all'



COPY bifrost_sudoers /etc/sudoers.d/kolla_bifrost_sudoers

RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_bifrost_sudoers \
    && chown -R bifrost:bifrost /bifrost

