FROM tor2/centos-source-kube-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)

ENV KUBERNETES_COMPONENT=kube-proxy

RUN true \
    && curl -L ${KUBERNETES_DOWNLOAD_ROOT}/${KUBERNETES_COMPONENT} -o /usr/bin/${KUBERNETES_COMPONENT} \
    && chmod +x /usr/bin/${KUBERNETES_COMPONENT}

# Clear any customisation by Kolla to entrypoint & command
ENTRYPOINT []
CMD []