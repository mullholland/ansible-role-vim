# [vim](#vim)

Installs and configures vim.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-vim/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-vim/actions)|[![gitlab](https://gitlab.com/opensourceunicorn/ansible-role-vim/badges/master/pipeline.svg)](https://gitlab.com/opensourceunicorn/ansible-role-vim)|[![quality](https://img.shields.io/ansible/quality/56823)](https://galaxy.ansible.com/mullholland/vim)|[![downloads](https://img.shields.io/ansible/role/d/56823)](https://galaxy.ansible.com/mullholland/vim)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-vim.svg)](https://github.com/mullholland/ansible-role-vim/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-vim/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  roles:
    - role: "mullholland.vim"
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/mullholland/ansible-role-vim/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: true

  tasks:
    - name: Debian/Ubuntu | update apt cache
      ansible.builtin.apt:
        update_cache: true
      when: ansible_os_family == "Debian"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-vim/blob/master/defaults/main.yml):

```yaml
---
# Should vim be the default (global) editor?
vim_default_editor: true

# global vim configuration values
# A small collection of the settings i use at the moment
# feel free to test and change these
# syntax on => adds syntax highlighting
# set expandtab => insert space characters whenever the tab key is pressed
# set shiftwidth=2 => change the number of space characters inserted for indentation
# set softtabstop=2 => cause <Tab> and <BS> to insert and delete the correct number of spaces
# set autoindent => autoindent essentially tells vim to apply the indentation of the current line to the next

vim_config:
  - "syntax on"
  - "set expandtab"
  - "set shiftwidth=2"
  - "set softtabstop=2"
  - "set autoindent"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-vim/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/mullholland/ansible-role-vim/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/mullholland/docker-centos-systemd/general)|all|
|[Amazon](https://hub.docker.com/repository/docker/mullholland/docker-amazonlinux-systemd/general)|Candidate|
|[Fedora](https://hub.docker.com/repository/docker/mullholland/docker-fedora-systemd/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/mullholland/docker-ubuntu-systemd/general)|all|
|[Debian](https://hub.docker.com/repository/docker/mullholland/docker-debian-systemd/general)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-vim/issues)

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-vim/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)

Please consider [sponsoring me](https://github.com/sponsors/mullholland).
