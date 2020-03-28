# Ansible Role: Docker CE

[![Build Status](https://travis-ci.com/marverix/ansible-role-docker-ce.svg?branch=master)](https://travis-ci.com/marverix/ansible-role-docker-ce)
![Ansible Quality Score](https://img.shields.io/ansible/quality/47502)
![Ansible Role](https://img.shields.io/ansible/role/47502)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

Ansible role that installs on linux Docker CE + Docker Compose + Python Docker SDK.

## Requirements

* Python
* pip

## Role Variables

Variable | Description | Default Value
--- | --- | ---
`docker_sdk_version` | Version of Python Docker SDK to be installed | `4.2.0`
`docker_compose_version` | Version of Docker Compose to be installed | `1.25.4`
`docker_user` | User that should be allowed to use Docker | _ansible_user_id_

## Dependencies

None

## Example Playbook

```yml
---
- hosts: all
  roles:
    - marverix.docker-ce

```

## License

ISC

## Thanks

To be honest **after** I wrote this role, learnt Molecule, spend couple hours etc...
I realized that https://github.com/geerlingguy/ansible-role-docker also can install
Docker Compose... Welp... It happens. Mentioned role is probably more mature, but
I didn't wanted to just throw away my work and time. If this role will help you - then great!
