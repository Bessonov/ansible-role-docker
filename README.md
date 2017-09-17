Ansible role for installation or update docker-engine from docker project apt repository
========================================================================================

[![Project is](https://img.shields.io/badge/Project%20is-fantastic-ff69b4.svg)](https://github.com/Bessonov/ansible-role-docker)
[![Build Status](https://travis-ci.org/Bessonov/ansible-role-docker.svg?branch=master)](https://travis-ci.org/Bessonov/ansible-role-docker)
[![License](http://img.shields.io/:license-MIT-blue.svg)](https://raw.githubusercontent.com/Bessonov/ansible-role-docker/master/LICENSE.txt)


This role:
- Import apt-key from docker project
- Install or update docker-engine
- Restart docker-engine

See also:
- [ansible docker-compose role](https://galaxy.ansible.com/Bessonov/docker-compose/) and
- [ansible docker-swarm role](https://galaxy.ansible.com/Bessonov/docker-swarm/).

Requirements
------------

No special requirements.

Role Variables
--------------

(optional) `docker_engine_version` specifies docker-engine version. You can also downgrade version, but be aware that docker doesn't like this and can fail to start or to work properly.

(optional) `docker_engine_allow_non_root` specifies a list with users, which should be added to `docker` group for non root access to docker. Users need to relogin or use `newgrp docker` to activate group for current shell. Be aware of security risk, because it's same as to give a root access to users.

Dependencies
------------

No dependencies.

Example Playbook
----------------

Install role globally with:

    ansible-galaxy install Bessonov.docker

or locally:

    ansible-galaxy install --roles-path roles Bessonov.docker

Playbook:

    - hosts: servers
      roles:
         - Bessonov.docker

or with parameters:

    - hosts: servers
      roles:
         - Bessonov.docker
           # optional set docker version
           docker_engine_version: 17.06.2

License
-------

The MIT License (MIT)

Copyright (c) 2016, Anton Bessonov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
