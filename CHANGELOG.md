# Changelog

## 8.3.0+1.6.5

- **BREAKING**
  - remove Ubuntu 18.04 support (reached EOL)
  - remove Debian 10 support (reached EOL)

- **UPDATE**
  - Update `cfssl` tools to version 1.6.5
  - add Debian 12 support
  - update Github workflow

- **MOLECULE**
  - fix ansible-lint issues in `converge.yml`

## 8.2.0+1.6.4

- **UPDATE**
  - Update `cfssl` tools to version 1.6.4
  - Add support for Ubuntu 22.04
  - Add verify step for Molecule

## 8.1.0+1.6.3

- Update `cfssl` tools to version 1.6.3
- add Github release action to push new release to Ansible Galaxy
- add `.yamllint`

## 8.0.1+1.6.2

- Update `cfssl` tools to version 1.6.2
- tasks/main.yml: use FQDN Ansible module name
- meta/main.yml: update `min_ansible_version` to `2.9` / add `role_name` and `namespace`

## 8.0.0+1.6.1

- Update `cfssl` tools to version 1.6.1
- Add support for Debian 10 (Buster) + 11 (Bullseye)
- Remove Ubuntu 16.04 (Xenial) support

## 7.1.0+1.6.0

- Update `cfssl` tools to version 1.6.0

## 7.0.0+1.5.0

- Update `cfssl` tools to version 1.5.0
- Added molecule test

## 6.0.0+1.4.1

- Update `cfssl` tools to version 1.4.1

## 6.0.0+1.4.0

- Renamed `cfssl_checksum_url` to `cfssl_checksum_url`

## 5.0.1+1.4.0

- Role requires Ansible version >= 2.7 now

## 5.0.0+1.4.0

- Update `cfssl` tools to version 1.4.0
- Since Cloudflare changed the way how to distribute binaries it's no longer possible to use `cfssl` binaries before version 1.4.0. If you need older binaries you can clone this Github repository and checkout `v4.0.0+1.2.0` branch
- Added new binaries: `cfssl-bundle`,`cfssl-certinfo`,`cfssl-newkey`,`cfssl-scan`, `mkbundle` and `multirootca`
- `cfssl_version` changed to `1.4.0`
- `cfssl_checksum` and `cfssljson_checksum` variables removed as they're no longer needed (replaced by `cfssl_checksum_url`)
- `cfssl_checksum_url` specifies the URL to a file that contains the SHA256 checksums for the various `cfssl` binaries
- `cfssl_arch` variable only supports `amd64` at the moment. Other architectures no longer supported

## Tags removed - no functionality change

- Removed all tags before `3.0.0+1.2.0`. That was needed because Ansible Galaxy don't work with version tags that don't respect semantic versioning scheme (SemVer)

## 4.0.0+1.2.0

- allow other architectures to download
- checksum as variable and for `cfssl` and `cfssljson` binary
- add Archlinux as supported platform

## 3.0.0+1.2.0

- use correct semantic versioning as described in [semver](https://semver.org). Needed for Ansible Galaxy importer as it now insists on using semantic versioning.
- moved changelog entries to separate file
- make Ansible linter happy
- no major changes but decided to start a new major release as versioning scheme changed quite heavily

## v2.0.3_r1.2.0

- update README

## v2.0.2_r1.2.0

- update documentation of variables / update README

## v2.0.1_r1.2.0

- variable values should be strings

## v2.0.0_r1.2.0

- removed `cfssl_conf_directory` variable (not needed as this role only installs the CFSSL binaries)

## v1.0.0_r1.2.0

- initial release
