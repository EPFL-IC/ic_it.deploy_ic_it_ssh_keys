IC-IT ssh keys deployment
=========

This role intends to install the ssh keys used by the IC-IT team into the authorized_keys file.

Requirements
------------

None.

I order to use this role, you'll need to reference it. Typically, this is done by creating a `requirements.yaml` file.

```yaml
---
roles:
  - name: ic_it.deploy_ic_it_ssh_keys
    src: git@github.com:EPFL-IC/ic_it.deploy_ic_it_ssh_keys.git
    scm: git
```

Then install the roles with `ansible-galaxy install -r requirements.yaml`.

Role Variables
--------------

| name | description | default |
| ----- |  ----------- | --------- |
| user_to_deploy_ssh_keys | for which user do we want to deploy the ssh keys? | root |
| ic_it_ssh_keys_present | list of ssh keys to add | list of keys |
| ic_it_ssh_keys_absent | list of ssh keys to remove | list of keys |

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - { role: ic_it.deploy_ic_it_ssh_keys, user_to_deploy_ssh_keys: root }
```

License
-------

BSD

Author Information
------------------

Emmanuel Jaep [EPFL profile](https://people.epfl.ch/emmanuel.jaep)
