FROM tor2/centos-source-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)







RUN usermod --append --home /usr/share/elasticsearch --groups kolla elasticsearch \
    && chsh --shell /bin/bash elasticsearch \
    && mkdir -p /usr/share/elasticsearch \
    && chown -R 42412:42412 /usr/share/elasticsearch



    

ENV JAVA_HOME /usr/lib/jvm/jre-1.7.0-openjdk/



RUN yum -y install java-1.7.0-openjdk elasticsearch && yum clean all
COPY elasticsearch_sudoers /etc/sudoers.d/kolla_elasticsearch_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

# NOTE: By default the shell of the elasticsearch user is /bin/false. We have to
# change the shell to /bin/bash to be able to run elasticsearch as a non-root user.
#
# https://discuss.elastic.co/t/running-as-non-root-user-service-wrapper-has-changed/7863

RUN chmod 755 /usr/local/bin/kolla_extend_start \
    && chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_elasticsearch_sudoers




USER elasticsearch