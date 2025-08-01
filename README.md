# Ansible Automation - Server Configuration

This repository contains Ansible playbooks to manage and automate server configuration tasks.

---

## 🛠 Prerequisites

- Ansible installed (>= 2.18)
- Python (>= 3.8) installed on the remote servers
- SSH access to target hosts
- Inventory file (`inventory.ini` or dynamic inventory script)

Install Ansible (Ubuntu):

```bash
sudo apt update
sudo apt install ansible -y
```


📁 Repository Structure

```bash

.
├── playbook.yml
├── inventory.ini
├── playbook.yml
└── README.md
```

1. Define Your Inventory
Edit the "inventory.ini" file:

```bash

[ec2]
192.168.1.10  ansible_user=ubuntu  ansible_ssh_private_key_file=~/.ssh/id_rsa  ansible_connection=ssh  ansible_user=distronix  ansible_python_interpreter=/usr/bin/python3.8
```
Or use dynamic inventory (e.g., AWS, GCP, etc.).

2. Run the Playbook
Basic syntax:
```bash

ansible-playbook -i inventory.ini playbook.yml -K
```

To run with extra variables:
```bash

ansible-playbook -i inventory.ini playbook.yml -e "env=production"
```

To check without applying changes (dry-run):

```bash

ansible-playbook -i inventory.ini playbook.yml --check
```


🔐 SSH Key Setup

Ensure your SSH key is copied to target servers:

```bash

ssh-copy-id user@host
```
Or set up in ~/.ssh/config or inventory.ini.


🧪 Example: Running a Sample Playbook

```bash

ansible-playbook -i inventory.ini check_resources.yml
```


🧾 License

MIT

```bash

# MIT License
# 
# Copyright (c) 2025 Biswarup Das
# 
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
# 
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
# 
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

```
