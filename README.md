CFSSL
=====

Installes CFSSL (CloudFlare's PKI toolkit). I used it as a lightweight CA for Kubernetes.

Role Variables
--------------

```
cfssl_version: R1.2
cfssl_bin_directory: /usr/local/bin
cfssl_ca_remote_directory: /etc/cfssl
cfssl_ca_local_directory: /etc/cfssl

ca_csr_cn: Kubernetes
ca_csr_key_algo: rsa
ca_csr_key_size: 2048
ca_csr_names_c: US
ca_csr_names_l: Portland
ca_csr_names_o: Kubernetes
ca_csr_names_ou: CA
ca_csr_names_st: Oregon

kubernetes_csr_cn: Kubernetes
kubernetes_csr_key_algo: rsa
kubernetes_csr_key_size: 2048
kubernetes_csr_names_c: US
kubernetes_csr_names_l: Portland
kubernetes_csr_names_o: Kubernetes
kubernetes_csr_names_ou: CA
kubernetes_csr_names_st: Oregon

kubernetes_cert_hosts:
  - 127.0.0.1
```
Change the `ca_csr_*` and `kubernetes_csr_*` variables to your need. The information is used for the CA and Kubernetes certificate signing request and included in your certifcates. Pay attention to `kubernetes_cert_hosts` list. Include all hosts here that use your certificate. Wildcards should work too e.g. `*.example.net`.

Example Playbook
----------------

```
- hosts: ca

  roles:
    - cfssl
```

License
-------

GNU GENERAL PUBLIC LICENSE Version 3

Author Information
------------------

http://www.tauceti.net
