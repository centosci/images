FROM docker.io/openshift/jenkins-slave-base-centos7:v3.11

MAINTAINER Brian Stinson <brian@bstinson.com>

COPY infrastructure.repo /etc/yum.repos.d/
COPY ssh_config /etc/ssh/ssh_config
RUN yum install -y https://cbs.centos.org/kojifiles/packages/python-cicoclient/0.4.4/1.el7/noarch/python-cicoclient-0.4.4-1.el7.noarch.rpm

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
