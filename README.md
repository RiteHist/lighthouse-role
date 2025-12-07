Lighthouse Role
=========

A simple Ansible role that installs VKCOM Lighthouse on a Debian-based machine.

Requirements
------------

The following packages must be installed on the machine before using this role:
-  nginx
-  git

Role Variables
--------------

| Variable | Description |
| -------- | ----------- |
| lighthouse_repo | Path to the Lighthouse repo |
| lighthouse_dir | Path to the directory that will contain Lighthouse |

Dependencies
------------

None

Example Playbook
----------------

```
- name: Install Lighthouse
  hosts: lighthouse
  become: true
  pre_tasks:
    - name: Install git
      ansible.builtin.apt:
        name: git
        update_cache: yes
        state: latest
    - name: Install nginx
      ansible.builtin.apt:
        name: nginx
        update_cache: yes
        state: latest
  roles:
    - lighthouse
```

License
-------

MIT
