[![Build Status](https://travis-ci.org/rhevm-qe-automation/ansible-role-seal.svg?branch=master)](https://travis-ci.org/rhevm-qe-automation/ansible-role-seal)

Seal
====

Performs sealing of Red Hat Enterprise Linux machine described at
[oVirt site](http://www.ovirt.org/documentation/how-to/virtual-machines/sealing-linux-vm/).

Requirements
------------

None

Role Variables
--------------

None

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
