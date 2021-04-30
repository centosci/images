FROM quay.io/fedora/fedora:35-x86_64

LABEL maintainer "Brian Stinson <brian@bstinson.com>, Vipul Siddharth <siddharthvipul@protonmail.com"

RUN dnf -y install python3-tox krb5-devel popt-devel python3-devel rpm-devel @c-development git poetry openssl-devel libcurl-devel openldap-devel npm libffi-devel rpm-build

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

COPY uid_entrypoint /uid_entrypoint

RUN chmod g=u /etc/passwd

USER 1001
