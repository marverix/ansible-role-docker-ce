# Ansible Role: Docker CE

[![Build Status](https://travis-ci.com/marverix/ansible-role-docker-ce.svg?branch=master)](https://travis-ci.com/marverix/ansible-role-docker-ce)
![Ansible Quality Score](https://img.shields.io/ansible/quality/47502)
![Ansible Role](https://img.shields.io/ansible/role/47502)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

Ansible role that installs on linux Docker CE + Docker Compose + Python Docker SDK.

## Features

- ✔️ Installing Docker Community Edition
  - Removes all old versions before
  - You can specify which user should be added to group `docker`
- ✔️ Installing Docker Compose
  - You can define which version should be installed
  - You can skip installation
  - Double-check that the newest version of `pip` is installed
- ✔️ Installing Python Docker SDK
  - You can define which version should be installed  
  - You can skip installation
- ✔️ Tested with Molecule Verify

## Supported Platforms

- ✔️ Ubuntu 16.04 (Xenial)
- ✔️ Ubuntu 18.04 (Bionic)
- ✔️ CentOS 7

## Requirements

- Python
- pip

## Role Variables

Variable | Description | Default Value
--- | --- | ---
`docker_sdk_version` | Version of Python Docker SDK to be installed. Set `no` to skip installation | `4.2.0`
`docker_compose_version` | Version of Docker Compose to be installed. Set `no` to skip installation | `1.25.4`
`docker_user` | User that should be allowed to use Docker | _ansible_user_id_

## Dependencies

None

## Example Playbook

1. The simplest one

    ```yml
    ---
    - hosts: all
      roles:
        - marverix.docker_ce

    ```

1. Skip installation of Docker Compose and Docker SDK

    ```yml
    ---
    - hosts: all
      roles:
        - role: marverix.docker_ce
          vars:
            docker_sdk_version: no
            docker_compose_version: no
    ```

## License

ISC

## Thanks

To be honest **after** I wrote this role, learnt Molecule, spend couple hours etc...
I realized that https://github.com/geerlingguy/ansible-role-docker also can install
Docker Compose... Welp... It happens. Mentioned role is probably more mature, but
I didn't wanted to just throw away my work and time. If this role will help you - then great!
