ansible-role-hostnames
=========

Install and configure SSH

Requirements
------------

This role has only been tested on EL 6 systems using Ansible 1.9.

Role Variables
--------------

Variables corresponding to sane SSH defaults are provided in defaults/main.yml. 

In addition, individual user accounts are configurable via the __role\_sshd\_users__ variable.

Example:
```
role_sshd_users:
- {
    username: 'john',
    ssh_folder: false, # If set to true, supply ssh files in files/home/{{ username }}/.ssh
    authorized_keys: false # If set to true, supply files/home/{{ username }}/.ssh/authorized_keys
}
```

Example Playbook
----------------

Override the above variables by modifying your project's group_vars or host_vars.

```
- hosts: servers
  roles:
    - { role: bitmotive.ansible-role-sshd, tags: "sshd,common" }
```

License
-------

MIT
