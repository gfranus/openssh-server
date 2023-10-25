# Ansible role: openssh-server
=========

Ansible role that installs/upgrades and configures OpenSSH-server with default configuration that meets CIS requirements.

## Main actions

* Install or upgrade OpenSSH-server package.
* Configure OpenSSH-server service.
* Enable OpenSSH-server service.
* Check if OpenSSH-server is responding on declared port.

## Requirements

#### Ansible version

Ansible >= 2.13

#### Python version

Python >= 3.9

#### Setup module
The role uses facts gathered by Ansible on the remote host. If you disable the Setup module in your playbook, the role will not work properly.

#### Root access
This role requires root access, so either configure it in your inventory files, run it in a playbook with a global `become: true` or invoke the role in your playbook like:
> site.yml:
```yaml
- hosts: servers
  become: true
  roles:
    - role: openssh-server
```

## Role Variables

All variables for this role are declared in the following files:
```yaml
  - default/main.yml
  - vars/*.yml
```

## Dependencies

This role does not have any dependencies.

## Example Playbook

Using the role is fairly straightforward:
> site.yml:
```yaml
- hosts: servers
  become: true
  roles:
    - role: openssh-server
      vars:
        - openssh_server_role_action: all
```

## License

This program is free software: you can redistribute it and/or modify it under the terms of the MIT License (MIT). See the LICENSE for details.

## Author Information

Grzegorz Franus