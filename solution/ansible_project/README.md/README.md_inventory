# Ansible Inventory File (inventory)

## Overview
This README provides an explanation of the structure and usage of the Ansible inventory file. The inventory file is used to define the hosts that Ansible will manage and group them into categories for easier management.

### Inventory Structure
[main_server]
Description: Group containing the main server host.
Hosts:
node1
[server1]
Description: Group containing hosts managed by server1.
Hosts:
node2
[server2]
Description: Group containing hosts managed by server2.
Hosts:
node3
[server3]
Description: Group containing hosts managed by server3.
Hosts:
node4

## Usage
To use this inventory file with Ansible, specify the location of the inventory file when running Ansible commands. You can use the -i option followed by the path to the inventory file. For example:

```bash
ansible-playbook -i inventory playbook.yml
```
This command will execute the playbook playbook.yml using the hosts defined in the inventory file.

## Host Groups
The inventory file organizes hosts into groups, which can be used to apply configurations or run tasks on specific sets of hosts. You can target groups or individual hosts in Ansible commands.

## References
Ansible Inventory Documentation
