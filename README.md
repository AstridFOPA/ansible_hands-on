Enterprise Ansible Automation- Multi -OS 

A complete end-to-end automation environment built with Ansible , designed to simulate real-world configuration management across multiple Linux operating systems.

This lab demonstrates how DevOps teams structure automation at scale using:

Modular roles

Handlers

Templates (Jinja2)

Variables (host/group variables)

Multi-OS logic (Ubuntu & CentOS)

Idempotent tasks

Service automation

Inventory segmentation (web servers, file servers, DB servers, etc.)

This project is perfect for DevOps, Cloud, SRE beginners or intermediates who want to master Ansible the way it is used in production environments.

🚀 Project Overview

This repository implements a realistic automation workflow:

Automated package installation (Apache, PHP, MariaDB, Samba)

SSH hardening using Jinja2 templates

Automatic creation of users & authorized keys

Service management with handlers

Directory creation & file deployment through templates

OS-specific logic using when:conditions

Fully modular role-based structure

🏗️ Repository Structure
ansible-hands-on/
│
├── inventory/               # Inventory files (hosts, groups)
├── host_vars/               # Host-specific variables
├── group_vars/              # (Optional) Group-specific variables
│
├── roles/
│   ├── base/                # Base configuration role (applied to all servers)
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   ├── handlers/
│   │   │   └── main.yml
│   │   ├── templates/
│   │   │   ├── sshd_config_ubuntu.j2
│   │   │   ├── sshd_config_centos.j2
│   │   │   └── test.txt.j2
│   │   └── vars/ (optional)
│   ├── web_servers/         # Web server tasks
│   ├── file_servers/        # File server tasks
│   └── db_servers/          # DB server tasks
│
├── playbooks/
│   ├── site.yml             # Main orchestration playbook
│   └── other playbooks...
│
└── README.md

⚙️ Technologies Used

Ansible 2.9+ / 2.12+

Ubuntu 20.04 / 22.04

CentOS 7 / 8

Jinja2 templating

YAML automation

SSH configuration management

📦 Features
✔️ 1. Multi-OS automation

Your roles automatically detect OS type and apply the right template (Ubuntu vs. CentOS).

✔️ 2. Template-based SSH configuration

Using templates like:

template:
  src: "{{ ssh_template_file }}"
  dest: /etc/ssh/sshd_config
  mode: "0644"
  owner: root
  group: root

✔️ 3. Handlers for service restarts

Example:

handlers:
  - name: restart_sshd
    service:
      name: sshd
      state: restarted


Triggered only when needed.

✔️ 4. Organized roles just like in companies

Each role manages its own tasks, handlers, and templates.

✔️ 5. Dynamic inventory classification

Servers are categorized as:

web_servers

file_servers

db_servers

workstations

📖 How to Use
1️⃣ Clone the repository
git clone https://github.com/YOUR_USERNAME/Enterprise-Ansible-Automation-Lab.git
cd Enterprise-Ansible-Automation-Lab

2️⃣ Test connection
ansible all -m ping -i inventory

3️⃣ Run the full configuration
ansible-playbook playbooks/site.yml --ask-become-pass

4️⃣ Run only one role
ansible-playbook playbooks/site.yml --limit web_servers

5️⃣ Run using tags
ansible-playbook playbooks/site.yml --tags ssh

📌Key Learnings from This Project

How to design Ansible roles the industry way

How templates dynamically generate configuration files

How handlers trigger only when needed

How to structure inventories for large environments

How to combine OS-specific tasks under one unified automation

How to automate 100+ servers with one command

🧠 Why This Project Matters

This repository demonstrates that you can:

Linux servers intelligently automaton

Write professional-grade Ansible roles

Structure configuration management like real DevOps teams

Handle multi-OS complexity

Produce maintainable, reusable automation architecture

It's a strong portfolio project for DevOps, Cloud, SRE, or Platform Engineering roles.

👤 Author

Astrid Loïc Baniaken Fopa
Cloud | DevOps | Automation Engineering
Laval / Montreal — Canada