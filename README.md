# Vagrant-Ansible Project

## Overview

The Vagrant-Ansible project is a configuration management project aimed at automating the setup and configuration of multiple virtual machines using Vagrant and Ansible. This project streamlines the process of setting up a multi-server environment with predefined configurations and automates the provisioning and management tasks using Ansible playbooks.

---
## Purpose

The purpose of this project is to provide a seamless and automated solution for setting up and managing virtual machine environments for various purposes such as development, testing, and deployment. By combining the power of Vagrant for virtual machine management and Ansible for configuration management, users can easily define and deploy complex infrastructure setups.

---
## Features

- **Automated Setup**: Vagrant simplifies the process of creating and managing virtual machines, while Ansible automates the configuration and provisioning tasks across multiple servers.

- **Modular Configuration**: The project is organized into separate roles and playbooks, allowing for easy customization and extension of configurations based on specific requirements.

- **Scalability**: Supports the setup of multiple virtual machines simultaneously, enabling users to create complex network topologies and distributed systems.

- **Flexibility**: Users can define their own configurations, install specific software packages, and customize settings to suit their needs. Additionally, the project supports the use of SSH key-based authentication for secure access to the virtual machines.

- **Centralized Configuration**: Uses Ansible to centrally manage configurations across all servers, ensuring consistency and reliability in the setup process.

---
## Project Structure

The project is structured as follows:

- **Vagrantfile**: Defines the configuration for virtual machines, including hostname, IP address, box image, and provisioning settings.

- **Ansible Playbooks**: Contains Ansible playbooks for configuring various aspects of the virtual machines, such as installing software packages, setting up services, and managing users.

- **Ansible Roles**: Organizes Ansible tasks, variables, and templates into reusable roles based on their functionality (e.g., base configuration, web server setup, file server setup, etc.).

- **Variables**: Stores variable files used by Ansible playbooks and roles to customize configurations and settings.

- **Templates**: Contains Jinja2 templates used by Ansible to generate configuration files dynamically.

- **Files**: Stores additional files required for configuration, such as SSH keys, scripts, and static content.

## Usage

To use the Vagrant-Ansible project:

- Clone the repository to your local machine.

- Navigate to the **[project directory](./solution/ansible_project)**

- Customize the Vagrantfile to define the desired virtual machine configurations.

- Configure Ansible playbooks, roles, and variables based on your requirements.

- Run vagrant up to create and provision the virtual machines.

- Access the virtual machines using SSH or other remote access methods.

## Dependencies 

- **Vagrant**: A tool for building and managing virtual machine environments.

Ansible: A configuration management and automation tool used for provisioning and managing infrastructure.

#Contributing

Contributions to the project are welcome! If you have any ideas, suggestions, or improvements, feel free to open an issue or submit a pull request on GitHub.
