ansible-role-cfssl
==================

Installes CFSSL (CloudFlare's PKI toolkit) binaries. I used it as a lightweight certificate authority (CA) for Kubernetes. This Ansible playbook is used in [Kubernetes the not so hard way with Ansible - certificate authority](https://www.tauceti.blog/post/kubernetes-the-not-so-hard-way-with-ansible-certificate-authority/).

Versions
--------

I tag every release and try to stay with [semantic versioning](http://semver.org). If you want to use the role I recommend to checkout the latest tag. The master branch is basically development while the tags mark stable releases. But in general I try to keep master in good shape too.

The tag `1.0.0+1.2.0` means that this is the release `1.0.0` of the Ansible role which uses release `1.2.0` of CFSSL.

Changelog
---------

see [CHANGELOG.md](https://github.com/githubixx/ansible-role-cfssl/blob/master/CHANGELOG.md)

Role Variables
--------------

```
# Specifies the version of CFSSL toolkit we want to download and use
cfssl_version: "R1.2"
# Checksum of "cfssl" binary
cfssl_checksum: "sha256:eb34ab2179e0b67c29fd55f52422a94fe751527b06a403a79325fed7cf0145bd"
# Checksum of "cfssljson" binary
cfssljson_checksum: "sha256:1c9e628c3b86c3f2f8af56415d474c9ed4c8f9246630bd21c3418dbe5bf6401e"
# The directory where CFSSL binaries will be installed
cfssl_bin_directory: "/usr/local/bin"
# Owner of "cfssl/cfssljson" binary
cfssl_owner: "root"
# Group of "cfssl/cfssljson" binary
cfssl_group: "root"
# Operarting system on which "cfssl/cfssljson" should run on
cfssl_os: "linux" # use "darwin" for MacOS X, "windows" for Windows
# Processor architecture "cfssl/cfssljson" should run on
cfssl_arch: "amd64" # other possible values: "386","arm64"
```

Example Playbook
----------------

```
- hosts: cfssl-hosts
  roles:
    - githubixx.cfssl
```

License
-------

GNU GENERAL PUBLIC LICENSE Version 3

Author Information
------------------

http://www.tauceti.blog
