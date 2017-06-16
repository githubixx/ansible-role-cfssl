ansible-role-cfssl
==================

Installes CFSSL (CloudFlare's PKI toolkit) binaries locally. I used it as a lightweight certificate authority (CA) for Kubernetes. This Ansible playbook is used in [Kubernetes the not so hard way with Ansible (at Scaleway) - part 4 - certificate authority](https://www.tauceti.blog/post/kubernetes-the-not-so-hard-way-with-ansible-at-scaleway-part-4/).

Role Variables
--------------

```
cfssl_version: R1.2
cfssl_bin_directory: /usr/local/bin
cfssl_conf_directory: /etc/cfssl
```

`cfssl_version` determines the version to download. `cfssl_bin_directory` specifices where to put the "cfssl" binary. In `cfssl_conf_directory` the CA files and other generated certificates will be stored.

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
