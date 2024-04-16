# ansible-role-cfssl

Installes CFSSL (CloudFlare's PKI toolkit) binaries. I used it as a lightweight certificate authority (CA) for Kubernetes. This Ansible playbook is used in [Kubernetes the not so hard way with Ansible - certificate authority](https://www.tauceti.blog/posts/kubernetes-the-not-so-hard-way-with-ansible-certificate-authority/).

## Versions

I tag every release and try to stay with [semantic versioning](http://semver.org). If you want to use the role I recommend to checkout the latest tag. The master branch is basically development while the tags mark stable releases. But in general I try to keep master in good shape too.

The tag `8.3.0+1.6.5` means that this is the release `8.3.0` of the Ansible role which uses release `1.6.5` of CFSSL.

## Changelog

**Change history:**

See full [CHANGELOG.md](https://github.com/githubixx/ansible-role-cfssl/blob/master/CHANGELOG.md)

**Recent changes:**

## 8.3.0+1.6.5

- Update `cfssl` tools to version 1.6.5

## 8.2.0+1.6.4

- Update `cfssl` tools to version 1.6.4
- Add support for Ubuntu 22.04
- Add verify step for Molecule

## Installation

- Directly download from Github (Change into Ansible roles directory before cloning. You can figure out the role path by using `ansible-config dump | grep DEFAULT_ROLES_PATH` command):
`git clone https://github.com/githubixx/ansible-role-cfssl.git githubixx.cfssl`

- Via `ansible-galaxy` command and download directly from Ansible Galaxy:
`ansible-galaxy install role githubixx.cfssl`

- Create a `requirements.yml` file with the following content (this will download the role from Github) and install with
`ansible-galaxy role install -r requirements.yml` (change `version` if needed):

```yaml
---
roles:
  - name: githubixx.cfssl
    src: https://github.com/githubixx/ansible-role-cfssl.git
    version: 8.3.0+1.6.5
```

## Role Variables

```yaml
# Specifies the version of CFSSL toolkit we want to download and use
cfssl_version: "1.6.5"

# Checksum file
cfssl_checksum_url: "https://github.com/cloudflare/cfssl/releases/download/v{{ cfssl_version }}/cfssl_{{ cfssl_version }}_checksums.txt"

# The directory where CFSSL binaries will be installed
cfssl_bin_directory: "/usr/local/bin"

# Owner of the cfssl binaries
cfssl_owner: "root"

# Group of cfssl binaries
cfssl_group: "root"

# Operating system on which "cfssl/cfssljson" should run on
cfssl_os: "linux" # use "darwin" for MacOS X, "windows" for Windows

# Processor architecture "cfssl/cfssljson" should run on
cfssl_arch: "amd64" # the only supported architecture at the moment
```

## Testing

This role has a small test setup that is created using [molecule](https://github.com/ansible-community/molecule). To run the tests follow the molecule [install guide](https://molecule.readthedocs.io/en/latest/installation.html). Also ensure that a Docker daemon runs on your machine.

Assuming [Docker](https://www.docker.io) is already installed you need at least two Python packages:

```bash
pip3 install --user molecule
pip3 install --user molecule-docker
```

Afterwards molecule can be executed:

```bash
molecule converge
```

This will setup some Docker container with Ubuntu 18.04/20.04 and Debian 10/11 with `cfssl` installed.

To clean up run

```bash
molecule destroy
```

## Example Playbook

```yaml
- hosts: cfssl-hosts
  roles:
    - githubixx.cfssl
```

## License

GNU GENERAL PUBLIC LICENSE Version 3

## Author Information

[http://www.tauceti.blog](http://www.tauceti.blog)
