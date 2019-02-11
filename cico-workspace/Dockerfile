FROM quay.io/openshift/origin-jenkins-agent-base:v4.0

MAINTAINER Brian Stinson <brian@bstinson.com>

RUN yum install -y pip
RUN pip install python-cicoclient

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
