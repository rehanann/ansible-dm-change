spk83.docker-provision-thinpool
===============================

Creates a thinpool logical volume to use with devicemapper storage driver in direct-lvm mode with docker engine.

To verfiy if the role executed successfully, run following command on target machine
```
lvs -o+seg_monitor
```

Role follows instructions from [here](https://docs.docker.com/engine/userguide/storagedriver/device-mapper-driver/#/configure-direct-lvm-mode-for-production)

Requirements
------------

See [meta/main.yml](meta/main.yml)

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml)

Dependencies
------------

See [meta/main.yml](meta/main.yml)

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - spk83.docker-provision-thinpool
```

License
-------

MIT

Author Information
------------------

Vishal Shah vishal.shah@nyu.edu
