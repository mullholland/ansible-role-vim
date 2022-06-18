# [vim](#vim)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-vim/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-vim/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-vim/badges/master/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-vim)|[![quality](https://img.shields.io/ansible/quality/unset)](https://galaxy.ansible.com/mullholland/vim)|

Installs and configures vim.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
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


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  roles:
    - role: "mullholland.vim"
```

The machine needs to be prepared in CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: true

  tasks:
    - name: Debian/Ubuntu | Install cron for Backupscript
      ansible.builtin.apt:
        update_cache: true
      when: ansible_os_family == "Debian"
```





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [debian9](https://hub.docker.com/r/mullholland/docker-molecule-debian9)
-   [debian10](https://hub.docker.com/r/mullholland/docker-molecule-debian10)
-   [debian11](https://hub.docker.com/r/mullholland/docker-molecule-debian11)
-   [ubuntu1804](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu1804)
-   [ubuntu2004](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2004)
-   [ubuntu2204](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2204)
-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos-stream8](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream8)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)
-   [fedora35](https://hub.docker.com/r/mullholland/docker-molecule-fedora35)
-   [fedora36](https://hub.docker.com/r/mullholland/docker-molecule-fedora36)
-   [rockylinux8](https://hub.docker.com/r/mullholland/docker-molecule-rockylinux8)
-   [almalinux8](https://hub.docker.com/r/mullholland/docker-molecule-almalinux8)
-   [amazonlinux](https://hub.docker.com/r/mullholland/docker-molecule-amazonlinux)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous versions.
-   The current version.
-   The [devel](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-devel-from-github-with-pip) version.





If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-vim/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
