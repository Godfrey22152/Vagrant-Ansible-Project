
# Overview

This README provides an overview of the `roles` Ansible role. This directory contains various subdirectories, each representing a different functionality or set of tasks to be executed on different servers. The subdirectories includes **[base](./base)**, **[main_server](./main_server)**, **[server1](./server1)**, **[server2](./server2)**, and **[server3](./server3)**

---
## Directory Structure

- **[base](./base)**: Contains tasks that are compulsory and should be executed on all servers.
- **[main_server](./main_server)**: Contains tasks specific to the `main server`.
- **[server1](./server1)**: Contains tasks specific to `server1`.
- **[server2](./server2)**: Contains tasks specific to `server2`.
- **[server3](./server3)**: Contains tasks specific to `server3`.

---
## Functionality

- **`Base Directory`**:
Contains tasks that are common and mandatory for all servers.
Tasks may include setting up basic configurations, installing common packages, etc.

- **Main Server Directory; `main_server`**:
Contains tasks specific to the `main server`. Tasks may include creating users, copying custom-made configuration files, adding users to the sudoers file, etc.

- **Server1 Directory `server1`**:
Contains tasks specific to `server1`. Tasks may include server-specific configurations, user management, etc.

- **Server2 Directory, `server2`**:
Contains tasks specific to `server2`. Tasks may include server-specific configurations, user management, etc.

- **Server3 Directory `server3`**:
Contains tasks specific to `server3`. Tasks may include server-specific configurations, user management, etc.

---
## Usage
To use this Ansible role, include it in your playbook and specify the appropriate subdirectories depending on the functionality needed for each server. For example:

```yaml
- name: Apply roles role
  hosts: all
  roles:
    - role: roles/base
    - role: roles/main_server
    - role: roles/server1
    - role: roles/server2
    - role: roles/server3
```

## Note:
Each directory within the `roles` are well-organized into `files`, `tasks`, and `variables`, ensuring a neat structure and easy-to-use playbook.
This structure helps in maintaining server-specific configurations and reduces the chances of errors.


## Resources
Checkout Ansible **[Documentation](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html)** for further guidance. 
