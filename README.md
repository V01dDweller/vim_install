# vim8_install

**Last updated**: 7/31/2022

Ansible role. Installs Vim from source-master on EL 7 Linux to
`/usr/local/bin/vim`.

- Internet connection
## Requirements

## Dependencies
None.

**1. Install the role**
```cmd
## Example Usage
ansible-galaxy install V01dDweller.vim8_install
```

This installs the role to ~/.ansible/roles. Alternatively, use '-p' to install
to another path, e.g.:

```cmd
ansible-galaxy install V01dDweller.vim8_install -p <path-to-project>/roles
```

**2. Create a short playbook**
```cmd
touch vim_install.yml
```
... and add the following:

```yaml
# file: vim_install.yml
---
- name: Install Vim 8
  hosts: all
  become: true
  roles:
    - role: V01dDweller.vim8_install
      tags: vim
```

**3. Run the Playbook**

```cmd
ansible-playbook vim_install.yml
```

**4. Validate**

```
$vim -version
VIM - Vi IMproved 8.2 (2019 Dec 12, compiled Mar 17 2020 02:51:26)
Garbage after option argument: "-version"
More info with: "vim -h"
```

## License
BSD

Written by V01dDweller in 2020.
## Author Information

