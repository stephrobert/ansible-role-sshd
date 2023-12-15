# stephrobert.sshd

[![Maintainer](https://img.shields.io/badge/maintained%20by-stephrobert-e00000?style=flat-square)](https://github.com/stephrobert)
[![License](https://img.shields.io/github/license/stephrobert/ansible-role-lynis?style=flat-square)](https://github.com/stephrobert/ansible-role-lynis/blob/main/LICENSE)
[![Release](https://img.shields.io/github/v/release/stephrobert/ansible-role-lynis?style=flat-square)](https://github.com/stephrobert/ansible-role-lynis/releases)
[![Status](https://img.shields.io/github/workflow/status/stephrobert/ansible-role-lynis/Ansible%20Molecule?style=flat-square&label=tests)](https://github.com/stephrobert/ansible-role-lynis/actions?query=workflow%3A%22Ansible+Molecule%22)
[![Ansible Galaxy](https://img.shields.io/badge/ansible-galaxy-black.svg?style=flat-square&logo=ansible)](https://galaxy.ansible.com/stephrobert/sshd)[![Ansible version](https://img.shields.io/badge/ansible-%3E%3D2.10-black.svg?style=flat-square&logo=ansible)](https://github.com/ansible/ansible)

⭐ Star us on GitHub — it motivates us a lot!

Install sshd

**Platforms Supported**:

| Platform | Versions |
|----------|----------|
| Debian | bullseye |
| Ubuntu | jammy |

## ⚠️ Requirements

Ansible >= 2.11.

### Ansible role dependencies

None.

## ⚡ Installation

### Install with Ansible Galaxy

```shell
ansible-galaxy install stephrobert.sshd
```

### Install with git

If you do not want a global installation, clone it into your `roles_path`.

```bash
git clone git@github.com:stephrobert/ansible-role-lynis.git  stephrobert.sshd
```

But I often add it as a submodule in a given `playbook_dir` repository.

```bash
git submodule add git@github.com:stephrobert/ansible-role-lynis.git roles/stephrobert.sshd
```

As the role is not managed by Ansible Galaxy, you do not have to specify the
github user account.

### ✏️ Example Playbook

Basic usage is:

```yaml
- hosts: all
  roles:
    - role: stephrobert.sshd
      vars:
        sshd_allowagentforwarding: 'no'
        sshd_allowtcpforwarding: 'no'
        sshd_allowusers: vagrant
        sshd_banner: /etc/issue.net
        sshd_casignaturealgorithms: sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512,rsa-sha2-256
        sshd_ciphers: chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr
        sshd_clientalivecountmax: 3
        sshd_clientaliveinterval: 300
        sshd_config_file_path: /etc/ssh/sshd_config.d/20-sshd-hardened.conf
        sshd_gssapikexalgorithms: gss-curve25519-sha256-,gss-group16-sha512-
        sshd_hostbasedacceptedalgorithms: sk-ssh-ed25519-cert-v01@openssh.com,ssh-ed25519-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-512,rsa-sha2-256-cert-v01@openssh.com,rsa-sha2-256
        sshd_hostbasedauthentication: 'no'
        sshd_hostkeyalgorithms: sk-ssh-ed25519-cert-v01@openssh.com,ssh-ed25519-cert-v01@openssh.com,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512,rsa-sha2-256
        sshd_ignorerhosts: 'yes'
        sshd_keepalive: 'no'
        sshd_kexalgorithms: sntrup761x25519-sha512@openssh.com,curve25519-sha256,curve25519-sha256@libssh.org,gss-curve25519-sha256-,diffie-hellman-group16-sha512,gss-group16-sha512-,diffie-hellman-group18-sha512,diffie-hellman-group-exchange-sha256
        sshd_logingracetime: 60
        sshd_loglevel: INFO
        sshd_macs: hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com,umac-128-etm@openssh.com
        sshd_maxauthtries: 3
        sshd_maxsessions: 2
        sshd_maxstartups: 10:30:60
        sshd_permitemptypasswords: 'no'
        sshd_permitrootlogin: 'no'
        sshd_permituserenvironment: 'no'
        sshd_pubkeyacceptedalgorithms: sk-ssh-ed25519-cert-v01@openssh.com,ssh-ed25519-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-512,rsa-sha2-256-cert-v01@openssh.com,rsa-sha2-256
        sshd_x11forwarding: 'no'
        
```

## ⚙️ Role Variables

Variables are divided in three types.

The **default vars** section shows you which variables you may
override in your ansible inventory. As a matter of fact, all variables should
be defined there for explicitness, ease of documentation as well as overall
role manageability.

The **context variables** are shown in section below hint you
on how runtime context may affects role execution.

### Default variables
Role default variables from `defaults/main.yml`.

| Variable Name | Value |
|---------------|-------|
| sshd_config_file_path | /etc/ssh/sshd_config.d/20-sshd-hardened.conf |
| sshd_clientalivecountmax | 3 |
| sshd_clientaliveinterval | 300 |
| sshd_hostbasedauthentication | no |
| sshd_keepalive | no |
| sshd_x11forwarding | no |
| sshd_loglevel | INFO |
| sshd_allowtcpforwarding | no |
| sshd_logingracetime | 60 |
| sshd_maxsessions | 2 |
| sshd_maxstartups | 10:30:60 |
| sshd_permitemptypasswords | no |
| sshd_maxauthtries | 3 |
| sshd_permitrootlogin | no |
| sshd_ignorerhosts | yes |
| sshd_allowagentforwarding | no |
| sshd_permituserenvironment | no |
| sshd_banner | /etc/issue.net |
| sshd_ciphers | chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr |
| sshd_kexalgorithms | sntrup761x25519-sha512@openssh.com,curve25519-sha256,curve25519-sha256@libssh.org,gss-curve25519-sha256-,diffie-hellman-group16-sha512,gss-group16-sha512-,diffie-hellman-group18-sha512,diffie-hellman-group-exchange-sha256 |
| sshd_macs | hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com,umac-128-etm@openssh.com |
| sshd_allowusers | vagrant |
| sshd_hostkeyalgorithms | sk-ssh-ed25519-cert-v01@openssh.com,ssh-ed25519-cert-v01@openssh.com,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512,rsa-sha2-256 |
| sshd_casignaturealgorithms | sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512,rsa-sha2-256 |
| sshd_gssapikexalgorithms | gss-curve25519-sha256-,gss-group16-sha512- |
| sshd_hostbasedacceptedalgorithms | sk-ssh-ed25519-cert-v01@openssh.com,ssh-ed25519-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-512,rsa-sha2-256-cert-v01@openssh.com,rsa-sha2-256 |
| sshd_pubkeyacceptedalgorithms | sk-ssh-ed25519-cert-v01@openssh.com,ssh-ed25519-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,ssh-ed25519,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-512,rsa-sha2-256-cert-v01@openssh.com,rsa-sha2-256 |

### Context variables

Those variables from `vars/*.{yml,json}` are loaded dynamically during task
runtime using the `include_vars` module.

Variables loaded from `vars/main.yml`.




## Author Information

none