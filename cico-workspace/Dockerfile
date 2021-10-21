FROM docker.io/openshift/jenkins-slave-base-centos7:v3.11

MAINTAINER Fabian Arrotin <arrfab@centos.org>

COPY infrastructure.repo /etc/yum.repos.d/
COPY RPM-GPG-KEY-CentOS-Infra /etc/pki/rpm-gpg/
COPY ssh_config /etc/ssh/ssh_config
RUN yum update -y && \
  yum install -y centos-release-ansible-29 && \
  yum install -y ansible python-cicoclient && \
  yum clean all

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
