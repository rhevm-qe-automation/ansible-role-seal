Seal
====

Performs sealing of Red Hat Enterprise Linux 7 machine

Requirements
------------

None

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: target
      roles:
         - { role: rhevm-qe-automation.ansible-role-seal }

Available are the following tags to be used with --skip-tags option:
- reset_hostname: Optionally, for environments where a host cannot determine its own name via DNS based lookups
    set HOSTNAME=localhost.localdomain
- delete_logs: [Optionally] Delete the build logs from /var/log.
- poweroff: shutdown the sealed machine

Author Information
------------------

Katerina Koukiou
kkoukiou@redhat.com
