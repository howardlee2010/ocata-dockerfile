FROM tor2/centos-source-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)



RUN curl -Lo /usr/local/bin/kubernetes-entrypoint https://github.com/stackanetes/kubernetes-entrypoint/releases/download/v0.1.1/kubernetes-entrypoint \
    && chmod 755 /usr/local/bin/kubernetes-entrypoint



CMD /usr/local/bin/kubernetes-entrypoint