Changelog
---------

**4.0.0+1.2.0**

- allow other architectures to download
- checksum as variable and for `cfssl` and `cfssljson` binary

**3.0.0+1.2.0**

- use correct semantic versioning as described in https://semver.org. Needed for Ansible Galaxy importer as it now insists on using semantic versioning.
- moved changelog entries to separate file
- make Ansible linter happy
- no major changes but decided to start a new major release as versioning scheme changed quite heavily

**v2.0.3_r1.2.0**

- update README

**v2.0.2_r1.2.0**

- update documentation of variables / update README

**v2.0.1_r1.2.0**

- variable values should be strings

**v2.0.0_r1.2.0**

- removed `cfssl_conf_directory` variable (not needed as this role only installs the CFSSL binaries)

**v1.0.0_r1.2.0**

- initial release
