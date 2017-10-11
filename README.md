role-cfssl
==========

Installes CFSSL (CloudFlare's PKI toolkit) binaries. I used it as a lightweight certificate authority (CA) for Kubernetes. This Ansible playbook is used in [Kubernetes the not so hard way with Ansible (at Scaleway) - part 4 - certificate authority](https://www.tauceti.blog/post/kubernetes-the-not-so-hard-way-with-ansible-at-scaleway-part-4/).

Versions
--------

I tag every release and try to stay with [semantic versioning](http://semver.org). If you want to use the role I recommend to checkout the latest tag. The master branch is basically development while the tags mark stable releases. But in general I try to keep master in good shape too.

The tag `v1.0.0_r1.2.0` means that this is the release `v1.0.0` of the Ansible role which uses release `r1.2.0` of CFSSL.

- v2.0.0_r1.2.0 - removed `cfssl_conf_directory` variable (not needed as this role only installs the CFSSL binaries)
- v1.0.0_r1.2.0 - initial release


Role Variables
--------------

```
cfssl_version: R1.2
cfssl_bin_directory: /usr/local/bin
```

`cfssl_version` determines the version to download. `cfssl_bin_directory` specifices where to put the "cfssl" binary.

Example Playbook
----------------

```
- hosts: k8s_ca
  roles:
    - githubixx.cfssl
```

License
-------

GNU GENERAL PUBLIC LICENSE Version 3

Author Information
------------------

http://www.tauceti.blog
