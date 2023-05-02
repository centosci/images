FROM quay.io/openshift/origin-jenkins-agent-base:latest

MAINTAINER Fabian Arrotin <arrfab@centos.org>

# "Convert" the image to CentOS Stream 8
# See: https://github.com/CentOS/sig-cloud-instance-images/blob/CentOS-8-Stream/docker/Dockerfile
RUN rm -f /etc/yum.repos.d/*.repo
RUN dnf download --repofrompath=centos,http://mirror.centos.org/centos/8-stream/BaseOS/x86_64/os/ --disablerepo=* --enablerepo=centos centos-stream-release centos-stream-repos centos-gpg-keys
RUN rpm -ivh --nodeps --replacefiles *.rpm && rm *.rpm \
    && rpm -e redhat-release \
    && dnf --setopt=tsflags=nodocs --setopt=install_weak_deps=false -y distro-sync \
    && dnf remove -y subscription-manager dnf-plugin-subscription-manager\
    && dnf install -y glibc-langpack-en iputils tree git\
    && dnf clean all

COPY infrastructure.repo /etc/yum.repos.d/
COPY RPM-GPG-KEY-CentOS-Infra /etc/pki/rpm-gpg/
COPY ssh_config /etc/ssh/ssh_config
RUN yum update -y && \
  yum install -y python39-pip && \
  yum install -y ansible-core && \
  yum clean all
RUN pip3.9 install duffy[client]
RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
