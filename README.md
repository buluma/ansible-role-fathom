# Ansible role [fathom](https://galaxy.ansible.com/ui/standalone/roles/buluma/fathom/documentation)

Fathom web analytics

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-fathom/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-fathom/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-fathom.svg)](https://github.com/buluma/ansible-role-fathom/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-fathom.svg)](https://github.com/buluma/ansible-role-fathom/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-fathom.svg)](https://github.com/buluma/ansible-role-fathom/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/fathom)](https://galaxy.ansible.com/ui/standalone/roles/buluma/fathom/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-fathom/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.fathom
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-fathom/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.repo_epel
      when:
        - (ansible_distribution == "Amazon" and
          ansible_distribution_major_version == "2") or
          (ansible_os_family == "RedHat" and
          ansible_distribution_major_version in [ "7", "8" ])
    - role: buluma.ca_certificates
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-fathom/blob/master/defaults/main.yml):

```yaml
---
# defaults file for fathom
fathom_binary_url: https://github.com/usefathom/fathom/releases/download/v1.3.1/fathom_1.3.1_linux_amd64.tar.gz
fathom_force_update: false

fathom_manage_service: true
fathom_service_state: started
fathom_service_enabled: true
fathom_service_user: root

fathom_directory: /opt/fathom
fathom_http_port: "9000"
fathom_database_name: fathom.db
fathom_secret: secret-string-here
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-fathom/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.repo_epel](https://galaxy.ansible.com/buluma/repo_epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-repo_epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-repo_epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-repo_epel.svg)](https://github.com/shadowwalker/ansible-role-repo_epel)|
|[buluma.nginx](https://galaxy.ansible.com/buluma/nginx)|[![Ansible Molecule](https://github.com/buluma/ansible-role-nginx/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-nginx/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-nginx.svg)](https://github.com/shadowwalker/ansible-role-nginx)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Ansible Molecule](https://github.com/buluma/ansible-role-ca_certificates/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-ca_certificates.svg)](https://github.com/shadowwalker/ansible-role-ca_certificates)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-fathom/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-fathom/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-fathom/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-fathom/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)

