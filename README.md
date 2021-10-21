# CentOS CI container images used in ocp.ci.centos.org

This repository contains several container images, used in OCP cluster for CI tenants:

  * [![cico-workspace](https://quay.io/repository/centosci/cico-workspace/status "cico-workspace")](https://quay.io/repository/centosci/cico-workspace) : jenkins java agent container connected to main jenkins server deployed in openshift. Based on centos container, with some tools added (like `cicoclient`)
  * [![python-tox](https://quay.io/repository/centosci/python-tox/status "python-tox")](https://quay.io/repository/centosci/python-tox) : fedora based container to test python code through tox
  * [![fedora-infra](https://quay.io/repository/centosci/fedora-infra/status "fedora-infra")](https://quay.io/repository/centosci/fedora-infra) : used by `fedora-infra` team for testing


