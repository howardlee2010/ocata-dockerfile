FROM tor2/centos-source-ironic-base:4.0.0
MAINTAINER Kolla Project (https://launchpad.net/kolla)






    
        
    
RUN /var/lib/kolla/venv/bin/pip --no-cache-dir install --upgrade -c requirements/upper-constraints.txt -r /ironic/driver-requirements.txt


RUN yum -y install dosfstoolsutil-linux qemu-img ipmitool parted gdisk psmisc fuse shellinabox socat && yum clean all




USER ironic