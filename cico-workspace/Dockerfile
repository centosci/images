FROM quay.io/openshift/origin-jenkins-agent-base:v4.0

MAINTAINER Brian Stinson <brian@bstinson.com>

RUN yum install -y epel-release
RUN yum install -y https://cbs.centos.org/kojifiles/packages/python-cicoclient/0.4.4/1.el7/noarch/python-cicoclient-0.4.4-1.el7.noarch.rpm

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
