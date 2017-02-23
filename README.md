ansible-authorized-key
===============

This role manage authorized-key

[![Ansible Galaxy](https://img.shields.io/ansible/role/15817.svg)](https://galaxy.ansible.com/salamachinas/authorized-key/)

Requirements
------------

This role requires Ansible 2.0 or higher and platform requirements are listed
in the metadata file.

Install
-------

```sh
ansible-galaxy install salamachinas.authorized-key
```

Example Playbook
----------------

```yaml
- name: provision servers
  hosts: all
  become: true
  roles:
    - { role: 'salamachinas.authorized-key', tags: 'authorized-key' }
  vars:
      authorized:
        - ansible
      users:
        name: ansible
        key: ssh-rsa key
```

Tests
-----

```sh
docker build -t test-ansible-authorized-key-centos7 -f tests/Dockerfile_centos7 --force-rm .
docker build -t test-ansible-authorized-key-debian7 -f tests/Dockerfile_debian7 --force-rm .
docker build -t test-ansible-authorized-key-debian8 -f tests/Dockerfile_debian8 --force-rm .
docker build -t test-ansible-authorized-key-ubuntu14 -f tests/Dockerfile_ubuntu14 --force-rm .
docker build -t test-ansible-authorized-key-ubuntu16 -f tests/Dockerfile_ubuntu16 --force-rm .
```
