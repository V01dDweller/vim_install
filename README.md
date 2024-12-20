# vim_install

![Ansible Role](https://img.shields.io/ansible/role/d/v01ddweller/vim_install)
![GitHub commit activity](https://img.shields.io/github/commit-activity/t/v01dDweller/vim_install)


[RIP Bram
Moolenar](https://arstechnica.com/gadgets/2023/08/bram-moolenaar-creator-of-the-beloved-vim-text-editor-has-passed-away/)

This Ansible role installs the latest version of Vim from [ source
](https://github.com/vim/vim) on the following Linux distributions:

* Alma Linux 8 and 9
* Ubuntu 20.04, 22.04 and 24.04

It will probably work for intermediate or alternate versions of the above, for
example, CentOS Stream 8, RHEL 9, Fedora 34+, Ubuntu 24.10, etc..

Vim is installed to `/usr/local/bin/vim,` and the role creates a
`/etc/profile.d/vim.sh` file to ensure that it takes precedence over
package-managed instances.

As of 2024 it is probably simpler to install Vim via the default package
manager as most modern distributions make a recent enough version of Vim
available. The original motivation for this project was to install newer
versions of Vim on the once popular, but now end-of-life, CentOS 7 which was
version locked to version 7.4.

Now this role is now more of a learning exercise for
[Ansible](https://www.ansible.com/), [Ansible
Galaxy](https://galaxy.ansible.com) and [Ansible
Molecule](https://ansible.readthedocs.io/projects/molecule/).

## Requirements

* sudo-to-root for Ansible user on target host.

## Dependencies

None.

## Installation

### Ansible Galaxy

#### Global Install

Install the role to so it is available to all projects via `~/.ansible/roles`:

```bash
ansible-galaxy install V01dDweller.vim_install
```
#### Project Install

Use `-p` to install to your Ansible project directory, for example:

```bash
ansible-galaxy install V01dDweller.vim_install -p <path-to-project>/roles
```

### Git

#### Global Install

```bash
mkdir -p ~/.ansible/roles
git clone https://github.com/V01dDweller/vim_install.git ~/.ansible/roles
```
#### Project Install

```bash
git clone https://github.com/V01dDweller/vim_install.git <path-to-project>/roles
```

## Usage Example

### 1. Create a short playbook

```bash
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

### 2. Run the Playbook

```bash
ansible-playbook vim_install.yml
```

### 4. Validate

```bash
$ vim -version
VIM - Vi IMproved 9.1 (2024 Jan 02, compiled Nov 11 2024 20:26:13)
Garbage after option argument: "-version"
More info with: "vim -h"
```

## License

BSD

## Author Information

By V01dDweller

[modeline]: # ( vim: set number relativenumber textwidth=78 colorcolumn=80: )
