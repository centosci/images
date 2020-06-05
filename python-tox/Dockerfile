FROM fedora:33

LABEL maintainer "Brian Stinson <brian@bstinson.com>"

RUN dnf -y install python3-tox krb5-devel popt-devel python3-devel rpm-devel @c-development git poetry openssl-devel libcurl-devel openldap-devel npm libffi-devel

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
