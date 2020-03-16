FROM fedora:31

LABEL maintainer "Brian Stinson <brian@bstinson.com>"

RUN dnf -y install python3 glibc glibc-devel libstdc++ zlib-devel ncurses-devel libX11-devel libXrender libXrandr nspr-devel nss-devel svrcore-devel openldap-devel libdb-devel cyrus-sasl-devel icu libicu-devel gcc-c++ net-snmp-devel lm_sensors-devel bzip2-devel zlib-devel openssl-devel tcp_wrappers pam-devel systemd-units openldap-clients perl-Mozilla-LDAP nss-tools cyrus-sasl-gssapi cyrus-sasl-md5 libdb-utils perl-Socket perl-NetAddr-IP pcre-devel maven gtk3-devel glib2-devel libgudev1-devel json-glib-devel gobject-introspection-devel libudisks2-devel systemd-devel accountsservice-devel pam-devel autoconf libtool intltool jsl gtk-doc krb5-devel sshpass perl-Locale-PO perl-JSON glib-networking realmd udisks2 mdadm lvm2 sshpass tito firefox python-devel python3-devel pwgen openmpi-devel mpich2-devel pylint nodejs-less python-cherrypy python-sqlalchemy python-ldap python-pam python-fedora freeipa-python httpd mod_auth_mellon postgresql-server openssl mod_wsgi python-psycopg2 sssd libsss_simpleifp openldap-servers mod_auth_gssapi krb5-server socket_wrapper nss_wrapper krb5-workstation mod_ssl python-jwcrypto createrepo dia python3-pygit2 nosync liberasurecode-devel python-lxml ruby ruby-devel ruby-irb ruby-libs rubygem-bigdecimal rubygem-bundler rubygem-io-console rubygem-json rubygem-net-http-persistent rubygem-psych rubygem-rdoc rubygem-rmagick rubygem-thor rubygems rubypick iptables ledger rubygem-asciidoctor rubygem-builder rubygem-coderay rubygem-eventmachine rubygem-ffi rubygem-formatador rubygem-git rubygem-haml rubygem-listen rubygem-method_source rubygem-multi_json rubygem-nenv rubygem-pry rubygem-rake rubygem-rb-inotify rubygem-shellany rubygem-slop rubygem-tilt doxygen findutils gettext-devel keyutils-libs-devel libini_config-devel libselinux-devel libverto-devel libxml2 libxslt m4 pkgconfig popt-devel krb5-server-ldap valgrind perl-Fedora-VSP perl-generators libevent-devel libcmocka-devel gperftools-devel python3-mock python3-pyxdg python3-gobject-base python3-GitPython python3-createrepo_c bodhi-client python26 python3-lxml podman

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001


