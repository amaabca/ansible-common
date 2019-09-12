Role Name
=========

This role sets deploy user, push up sudoers and deployers keys, install logrotate and set vim as default text editor.

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
  datadog_api_token: <datadog_token>
deployer: <app_name>
deployer_home_dir: "/srv/{{ deployer }}"
root_user: <root_user_name> # optional
deployers_path: <path_to_deployers_ssh_public_key_template>
sudoers_path: <path_to_sudoers_ssh_public_key_template> # defaults to deployers_path
ssh_key_options: 'no-pty' # defaults to 'no-X11-forwarding,no-port-forwarding'. See https://man.openbsd.org/OpenBSD-current/man8/sshd.8#AUTHORIZED_KEYS_FILE_FORMAT.
```

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
