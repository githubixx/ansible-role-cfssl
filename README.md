ansible-role-cfssl
==================

Installes CFSSL (CloudFlare's PKI toolkit) binaries. I used it as a lightweight certificate authority (CA) for Kubernetes. This Ansible playbook is used in [Kubernetes the not so hard way with Ansible - certificate authority](https://www.tauceti.blog/post/kubernetes-the-not-so-hard-way-with-ansible-certificate-authority/).

Versions
--------

I tag every release and try to stay with [semantic versioning](http://semver.org). If you want to use the role I recommend to checkout the latest tag. The master branch is basically development while the tags mark stable releases. But in general I try to keep master in good shape too.

The tag `6.0.0+1.4.1` means that this is the release `6.0.0` of the Ansible role which uses release `1.4.1` of CFSSL.

Changelog
---------

see [CHANGELOG.md](https://github.com/githubixx/ansible-role-cfssl/blob/master/CHANGELOG.md)

Role Variables
--------------

```
# Specifies the version of CFSSL toolkit we want to download and use
cfssl_version: "1.4.1"
# Checksum file
cfssl_checksum_url: "https://github.com/cloudflare/cfssl/releases/download/v{{ cfssl_version }}/cfssl_{{ cfssl_version }}_checksums.txt"
# The directory where CFSSL binaries will be installed
cfssl_bin_directory: "/usr/local/bin"
# Owner of the cfssl binaries
cfssl_owner: "root"
# Group of cfssl binaries
cfssl_group: "root"
# Operarting system on which "cfssl/cfssljson" should run on
cfssl_os: "linux" # use "darwin" for MacOS X, "windows" for Windows
# Processor architecture "cfssl/cfssljson" should run on
cfssl_arch: "amd64" # the only supported architecture at the moment
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
