# Move Operations

A basic Ansible role to do Nutanix Move cutover operations.

## Required Variables

- Edit the `default/main.yml` file and set these to match your environment:

  - `move_ip`: [IP address of the Nutanix Move appliance]
  - `move_username`: [Nutanix Move admin account is always admin]
  - `move_password`: [The password to your account.  Note: You should not store this as clear text - use Ansible vault]

## Example Playbook - Base Playbook Options

```
---
- name: Move Operations
  hosts: localhost
  gather_facts: false
  tasks:
    - name: Move Operations
      include_role:
        name: move
      # vars can be also added in the defaults/main.yml file
      vars:
        vm_name: your vm name
        plan_name: your plan name
        # Supported Actions: cutover, test, retest, undotest, retry, discard, abort  
        action: cutover
```

## Author Information

Based on the Nutanix VM Provisioner role Created by Matthew Bach and Timothy Ling, from Red Hat.

Modified for Nutanix Move Operations by David Teague, Technical Marketing Engineer at Nutanix.

## License

Please see the [main license file](https://github.com/nutanixdev/ansible-move/blob/master/README.md) for this repository.
