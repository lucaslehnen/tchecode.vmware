Install role
-------------------------------------------------------------------

This role install VMWare Workstation.

Configure the variables
-----------------------

`vmware.workstation.url`: The path to the bundle (in `ansible.builtin.get_url` format).  
`vmware.workstation.serial_number`: The VMWare Workstation isn't Open Source, so, you need a serial number. Put it here.

```yaml
- hosts: all
  user: debian
  become: true
  gather_facts: false
  roles:
    - tchecode.vmware.install-ws
  vars:
    vmware:    
      workstation:
        url: "https://download3.vmware.com/software/wkst/file/VMware-Workstation-Full-16.2.1-18811642.x86_64.bundle"
        serial_number: "XXXXX-XXXXX-XXXXX-XXXXX-XXXXX"
```
