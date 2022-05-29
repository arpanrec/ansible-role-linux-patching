# Linux Patching (linux_patching)

Install all latest packages in Debian based systems. also Install basic utility tools for server.
Set timezone, locale, and loopback ip in server

## Role Variables

```yaml
- name: rv_linux_patching_upgrade_existing_packages
  description: If set to `true` Upgrade the existing packages in OS.
  required: no
  default: true
  type: bool
- name: rv_linux_patching_packages
  description: Install the packages in all the distributions.
  required: no
  default:
    [
      zip,
      unzip,
      net-tools,
      build-essential,
      tar,
      wget,
      curl,
      ca-certificates,
      sudo,
      systemd,
      telnet,
      gnupg2,
      apt-transport-https,
      lsb-release,
      software-properties-common,
      locales,
      "linux-headers-{{ansible_kernel}}",
      network-manager,
      gnupg2,
      gnupg,
      pigz,
      cron,
      acl,
    ]
  type: list[str]
- name: rv_linux_patching_timezone
  description: Set the ZoneTime info in server.
  required: no
  default: Asia/Kolkata
  type: str
- name: rv_linux_patching_hostname_fqdn
  description: Cluster / Public Host name.
  required: no
  type: str
```

## Example Playbook

```yaml
- name: Patch linux OS
  include_role:
    name: arpanrec.linux_patching
  vars:
    rv_linux_patching_upgrade_existing_packages: true
    rv_linux_patching_hostname_fqdn: s1-dev
```

## License

MIT
