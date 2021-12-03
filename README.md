# Ansible Collection - tchecode.vmware

[![wakatime](https://wakatime.com/badge/github/lucaslehnen/tchecode.vmware.svg)](https://wakatime.com/badge/github/lucaslehnen/tchecode.vmware)

It's an Ansible collection with roles to install VMWare Tools.

** For now, tested only by  amd64 hosts running Debian.

## Roles available

- `tchecode.vmware.install-ws`: Install VMWare Workstation.
- `tchecode.vmware.install-esxi`: Install VMWare ESXi inside a Workstation machine. ****WIP
- `tchecode.vmware.reset`: Reset all changes made by this collection

More info about these roles can be found in `roles/{role}` folder.

## How to use

Define your inventory in `hosts` file:
```
192.168.99.30
```

Create your playbook `site.yml`:

```YAML
- hosts: all
  user: ubuntu
  become: true
  gather_facts: false
  roles:
    - tchecode.vmware.install-ws
```

Run the playbook:

```
ansible-playbook -i hosts site.yml
```

To revert all changes, you can call the role `reset`. I Suggest another playbook, `reset.yml` for example:

```YAML
- hosts: all
  user: user
  become: true
  roles:
    - {role: reset, tags: [reset]}  
```
