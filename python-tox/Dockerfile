ARG fedora_version=rawhide
FROM fedora:$fedora_version

LABEL maintainer "Brian Stinson <brian@bstinson.com>"

RUN dnf -y install python3-tox python-tox krb5-devel popt-devel python-devel

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001