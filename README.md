ansible-role-gitlab
=========

Install gitlab on Docker behind an SSL proxy.

Requirements
------------

Requires `docker` and `docker-py`. This can be fulfilled through the following
Ansible roles:

``` yaml
- name: Converge
  hosts: all
  become: yes
  vars:
    pip_install_packages:
      - name: docker
  roles:
    - geerlingguy.pip
    - geerlingguy.docker

```

Role Variables
--------------

A description of the settable variables for this role should go here, including
any variables that are in defaults/main.yml, vars/main.yml, and any variables
that can/should be set via parameters to the role. Any variables that are read
from other roles and/or the global scope (ie. hostvars, group vars, etc.) should
be mentioned here as well.

Dependencies
------------

None

Example Playbook
----------------

``` yaml
---
- name: Converge
  hosts: all
  become: yes
  vars:
    pip_install_packages:
      - name: docker
    gitlab_external_url: https://mysite
  roles:
    - geerlingguy.pip
    - geerlingguy.docker
    - ansible-role-gitlab

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-activated-gitlab, x: 42 }
```

License
-------

MIT

Author Information
------------------

Ben Tomasini, Activated, Inc. - [btomasini@activated.io](mailto:btomasini@activated.io)
