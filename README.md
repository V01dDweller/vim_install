vim8\_install
=============
Ansible role. Installs Vim 8 from source-master on EL 7 Linux to
`/usr/local/bin/vim`.

Requirements
------------
- Internet connection

Dependencies
------------
None.

Example Usage
-------------
**1. Install the role**
```cmd
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

License
-------
BSD

Author Information
------------------
Written by V01dDweller in 2020.

