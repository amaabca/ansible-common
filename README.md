Role Name
=========

This role sets deploy user, push up sudoers and deployers keys, installs and set new relic monitorin, install logrotate and set vim as default text editor.

Requirements
------------

you will need:

1 - Datadog account and API key

2 - File with deployers ssh keys


Role Variables
--------------
Store the following in [a vault file](http://docs.ansible.com/ansible/playbooks_vault.html):

```yaml
secrets:
  datadog_api_token: yourdatadogtokenhere
  loggly:
    token: yourlogglytokenhere
```

Dependencies
------------

All configuration was done with rsyslogd 7.4.4.

Example Playbook
----------------

```bash
ansible-playbook tests/test.yml -i your_inventory_file
```

How to include this role:

```yaml
- hosts: servers
  roles:
    - ansible-common
```

License
-------

MIT

Author Information
------------------

www.ama.ab.ca, webmaster@ama.ab.ca