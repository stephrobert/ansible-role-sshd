# stephrobert.sshd

[![Maintainer](https://img.shields.io/badge/maintained%20by-stephrobert-e00000?style=flat-square)](https://github.com/stephrobert)
[![License](https://img.shields.io/github/license/stephrobert/ansible-role-sshd?style=flat-square)](https://github.com/stephrobert/ansible-role-sshd/blob/main/LICENSE)
[![Release](https://img.shields.io/github/v/release/stephrobert/ansible-role-sshd?style=flat-square)](https://github.com/stephrobert/ansible-role-sshd/releases)
[![Status](https://img.shields.io/github/workflow/status/stephrobert/ansible-role-sshd/Ansible%20Molecule?style=flat-square&label=tests)](https://github.com/stephrobert/ansible-role-sshd/actions?query=workflow%3A%22Ansible+Molecule%22)
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
git clone git@github.com:stephrobert/ansible-role-sshd.git  stephrobert.sshd
```

But I often add it as a submodule in a given `playbook_dir` repository.

```bash
git submodule add git@github.com:stephrobert/ansible-role-sshd.git roles/stephrobert.sshd
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
        sshd_config: {}
        
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
| sshd_config | {}<br> |

### Context variables

Those variables from `vars/*.{yml,json}` are loaded dynamically during task
runtime using the `include_vars` module.

Variables loaded from `vars/main.yml`.

| Variable Name | Value |
|---------------|-------|
| _sshd_config | AcceptEnv: LANG LC_*<br>AddressFamily: any<br>AllowAgentForwarding: false<br>AllowTcpForwarding: false<br>AllowUsers: ansible<br>AuthorizedKeysCommand: none<br>AuthorizedKeysCommandUser: nobody<br>AuthorizedKeysFile: .ssh/authorized_keys<br>AuthorizedPrincipalsFile: none<br>Banner: /etc/issue.net<br>ChrootDirectory: none<br>ClientAliveCountMax: 2<br>ClientAliveInterval: 300<br>Compression: false<br>ForceCommand: none<br>GSSAPIAuthentication: false<br>GSSAPICleanupCredentials: true<br>GatewayPorts: false<br>HostKey: /etc/ssh/ssh_host_rsa_key<br>HostbasedAuthentication: false<br>IgnoreRhosts: true<br>IgnoreUserKnownHosts: false<br>KbdInteractiveAuthentication: true<br>KerberosAuthentication: false<br>KerberosGetAFSToken: false<br>KerberosOrLocalPasswd: true<br>KerberosTicketCleanup: true<br>ListenAddress: 0.0.0.0<br>LogLevel: INFO<br>LoginGraceTime: 60<br>MaxAuthTries: 3<br>MaxSessions: 2<br>MaxStartups: 10:30:100<br>PasswordAuthentication: false<br>PermitEmptyPasswords: false<br>PermitRootLogin: false<br>PermitTTY: true<br>PermitTunnel: false<br>PermitUserEnvironment: false<br>PidFile: /var/run/sshd.pid<br>Port: 22<br>PrintLastLog: true<br>PrintMotd: true<br>PubkeyAuthentication: true<br>RekeyLimit: default 60s<br>StrictModes: true<br>Subsystem: sftp    /usr/lib/openssh/sftp-server<br>SyslogFacility: AUTH<br>TCPKeepAlive: false<br>UseDNS: false<br>UsePAM: false<br>VersionAddendum: none<br>X11DisplayOffset: 10<br>X11Forwarding: false<br>X11UseLocalhost: true<br> |



## Author Information

none