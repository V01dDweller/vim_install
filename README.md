# vim_install

Ansible role. Installs Vim from source-master on EL 7, Alma Linux 8, Ubuntu
Linux to `/usr/local/bin/vim`. Tested with CentOS 7, AlmaLinux 8, Ubuntu 20.04
(focal) and Ubuntu 22.04 (jammy)

## Requirements

* Internet connection
* Ansible user must be able to sudo to root

## Dependencies

None.

## Example Usage

### 1. Install the role

```cmd
ansible-galaxy install V01dDweller.vim_install
```

This installs the role to ~/.ansible/roles. Alternatively, use '-p' to install
to another path, e.g.:

```cmd
ansible-galaxy install V01dDweller.vim_install -p <path-to-project>/roles
```

### 2. Create a short playbook

```cmd
touch vim_install.yml
```

... and add the following:


```yaml
# file: vim_install.yml
---
- name: Install Vim
  hosts: all
  become: true
  roles:
    - role: V01dDweller.vim_install
      tags: vim
```

### 3. Run the Playbook

```cmd
ansible-playbook vim_install.yml
```

### 4. Validate

```cmd
$ vim -version
VIM - Vi IMproved 9.0 (2022 Jun 28, compiled Aug  4 2022 21:28:37)
Garbage after option argument: "-version"
More info with: "vim -h
```

## License

BSD

## Author Information

By V01dDweller

[modeline]: # ( vim: set textwidth=78 colorcolumn=80: )
