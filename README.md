Role Name
=========

Create a user for ansible, and lock down access to the root user.

Requirements
------------

None.

Role Variables
--------------

The following are the variables used by the role and their defaults.

```YAML
admin_user: ansible
admin_user_shell: /bin/bash
```

```YAML
admin_user_public_keys:
  - ~/.ssh/id_rsa.pub
```

It is crucial that a valid SSH key be added for the user since that is the only way to login as the user.

Dependencies
------------

None.

Example Playbook
----------------

Running the role is fairly straightforward. The only issue is that if access to
the root user has already been disabled, the role might fail to connect if run
again.

    - hosts: all
      remote_user: root
      roles:
         - { role: cdriehuys.lock-root, admin_user: ansible }

License
-------

MIT

Author Information
------------------

Chathan Driehuys (cdriehuys@gmail.com)
