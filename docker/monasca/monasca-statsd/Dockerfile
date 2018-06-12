FROM tor2/centos-source-monasca-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







ADD monasca-statsd-archive /monasca-statsd-source
# NOTE(SamYaple): <=1.3.0 do not have any packages in requirements.txt and that
# breaks pip. So removing constraints file.
RUN ln -s monasca-statsd-source/* monasca-statsd \
    && /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade /monasca-statsd







USER monasca
