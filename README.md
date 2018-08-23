ansible-role-gitlab
=========

Install gitlab on Docker behind an SSL proxy.

This role fulfills a narrow use case. Broader use will require more
configuraiton vairables.

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

| Name | Default | Description |
| --- | --- | --- |
| gitlab_user | gitlab | User to create |
| gitlab_base_path | /var/lib/gitlab | Base path for gitlab subdirectories |
| gitlab_data_path | "{{ gitlab_base_path }}/data" | Location of data on the host |
| gitlab_logs_path | "{{ gitlab_base_path }}/logs" | Location of logs on the host |
| gitlab_config_path | {{ gitlab_base_path }}/config" | Location of configuration on the host |
| gitlab_external_url | http://localhost | External URL |
| gitlab_docker_image | gitlab/gitlab-ce:11.2.0-ce.0 | Gitlab image to run |
| gitlab_http_port | 8080 | HTTP port exposed on host |

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

```

License
-------

MIT

Author Information
------------------

Ben Tomasini, Activated, Inc. - [btomasini@activated.io](mailto:btomasini@activated.io)
