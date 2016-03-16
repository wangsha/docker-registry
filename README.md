docker-registry
========

[![Build Status](https://travis-ci.org/wangsha/docker-registry.svg?branch=master)](https://travis-ci.org/wangsha/docker-registry)
[![Ansible Galaxy](https://img.shields.io/badge/AnsibleGalaxy-wangsha.docker--registry-blue.svg)](https://galaxy.ansible.com/wangsha/docker-registry/)

Ansible role to manage and run docker registry:2.

No authentication is done here; the registry is supposed to sit behind a proxy,
which handles HTTPS and authentication.

Requirements
------------

This role has only been tested on Ubuntu 14.04. Since this uses Ansible's
docker module, you will need to ensure that a recent-ish version of `docker-py`
and `docker` are installed.


Examples
--------

Install this module from Ansible Galaxy into the './roles' directory:
```bash
ansible-galaxy install wangsha.docker-registry -p ./roles
```

Use it in a playbook as follows, assuming you already have docker setup:
```yaml
- hosts: 'servers'
  roles:
    - role: 'wangsha.docker-registry'
      become: true
```

Have a look at the [defaults/main.yml](defaults/main.yml) for role variables
that can be overridden! If you need a playbook to set Docker itself, have a
look at
[angstwad.docker_ubuntu](https://github.com/angstwad/docker.ubuntu) Galaxy
role.


Additional References
---------------------
- [Default docker image](https://hub.docker.com/_/registry/)
- [Tutorial: deploying a registry server](https://docs.docker.com/registry/deploying/)

License
-------

[MIT](LICENSE.txt)

Author Information
------------------
- blurrcat
- wangsha
