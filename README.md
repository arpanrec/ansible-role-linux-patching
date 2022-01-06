Linux Patching (linux_patching)
=========

Install all latest packages in Debian/Arch based systems. also Install basic utility tools for server.
Set timezone, locale, and loopback ip in server

Role Variables
--------------

`rv_linux_patching_upgrade_existing_packages`
  * Type: `boolean`
  * Default: `true`
  * Required: `false`
  * Description: If set to `true` Upgrade the existing packages in OS.

`rv_linux_patching_packages_{{  ansible_os_family  }}`
  * Type: `List[String]`
  * Default (rv_linux_patching_packages_Debian): `[zip, unzip, net-tools, tar, wget, curl, ca-certificates, sudo, systemd, telnet, gnupg2, apt-transport-https, lsb-release, software-properties-common, locales]`
  * Required: `false`
  * Description: Install the packages in all the distributions.

`rv_linux_patching_timezone`
  * Type: `String`
  * Default: `Asia/Kolkata`
  * Required: `false`
  * Description: Set the ZoneTime info in server.

`rv_linux_patching_hostipv4`
  * Type: `ipaddr`
  * Required: `false`
  * Description: Cluster / Public IP address.

`rv_linux_patching_hostname`
  * Type: `String`
  * Required: `false`
  * Description: Cluster / Public Host name.

`rv_linux_patching_hostdomain`
  * Type: `String`
  * Required: `false`
  * Description: Cluster / Public Domain name.

Example Playbook
----------------
```
- name: Patch linux OS
  include_role:
    name: linux_patching
  vars:
    rv_linux_patching_upgrade_existing_packages: true
    rv_linux_patching_hostname: s1-dev
    rv_linux_patching_hostdomain: sourceshift.org
```

License
-------

Apache License 2.0
