FROM quay.io/openshift/origin-jenkins-agent-base:latest

MAINTAINER Fabian Arrotin <arrfab@centos.org>

# "Convert" the image to Almalinux 8
# See: https://github.com/CentOS/sig-cloud-instance-images/blob/CentOS-8-Stream/docker/Dockerfile
RUN rm -f /etc/yum.repos.d/*.repo
RUN dnf download --repofrompath=almalinux,https://repo.almalinux.org/almalinux/8/BaseOS/x86_64/os/ --disablerepo=* --enablerepo=almalinux almalinux-release 
RUN rpm -e redhat-release --nodeps && /bin/rm -Rf /usr/share/redhat-release
RUN rpm -ivh --nodeps --replacefiles *.rpm && rm *.rpm \
    && dnf --setopt=tsflags=nodocs --setopt=install_weak_deps=false -y distro-sync \
    && dnf remove -y subscription-manager dnf-plugin-subscription-manager \
    && dnf remove -y java-11-openjdk-headless java-1.8.0-openjdk-headless \
    && dnf install -y glibc-langpack-en iputils tree git \
    && dnf clean all

COPY ssh_config /etc/ssh/ssh_config
RUN yum update -y && \
  yum install -y python3.11-pip && \
  yum install -y ansible-core && \
  yum clean all
RUN pip3.11 install duffy[client]
RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

# Converting to java 17 due to jenkins server 2.479 expecting at least java-17 now
RUN /usr/sbin/alternatives --remove java /usr/lib/jvm/jre-11-openjdk/bin/java && dnf install -y java-17-openjdk-headless
RUN sed -i 's/java-11/java-17/' /usr/local/bin/run-jnlp-client

USER 1001
