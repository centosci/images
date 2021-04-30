FROM quay.io/centos/centos/centos7

LABEL maintainer "Brian Stinson <brian@bstinson.com>"

RUN yum -y install epel-release
RUN yum -y install python3 python-tox krb5-devel popt-devel python3-devel rpm-devel git
RUN pip3 install poetry

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
