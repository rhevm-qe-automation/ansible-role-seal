[![Build Status](https://travis-ci.org/rhevm-qe-automation/ansible-role-seal.svg?branch=master)](https://travis-ci.org/rhevm-qe-automation/ansible-role-seal)

Seal
====

This role performs sealing steps for following operating systems:

* RedHat / CentOS  ([oVirt site](http://www.ovirt.org/documentation/how-to/virtual-machines/sealing-linux-vm/))
* Ubuntu / Debian

Requirements
------------

You need to have enabled [ControlMaster](http://docs.ansible.com/ansible/latest/intro_configuration.html#openssh-specific-settings)
under [ssh_connection] header in ansible configuration file.  
The defaults `ssh_args = -o ControlMaster=auto -o ControlPersist=60s` will work.

Role Variables
--------------

* **seal\_run\_containerized**

  This option allows `seal` role run inside of container, default=false.

  Problem is with `/etc/hostname` file which can not be renamed because it
  is being bind-mounted.

Dependencies
------------

None

Available tags
--------------

You can skip following sealing steps using `--skip-tags` option.

* **reset\_hostname**

  Tag is assigned to tasks which reset hostname.

* **delete\_logs**

  Tag is assigned to tasks which wipe out `/var/log/` directory.

* **poweroff**

  Tag is assigned to task which shutdown sealed machine.

Example Playbook
----------------

```yaml
---
- hosts: all
  remote_user: root
  roles:
    - { role: rhevm-qe-automation.ansible-role-seal }
```

Author Information
------------------

Katerina Koukiou
kkoukiou@redhat.com
