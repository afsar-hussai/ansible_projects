🚀 Ansible DevOps Journey: Web Server Automation
================================================

This repository documents my hands-on journey of mastering **Ansible**, **Cloud Infrastructure**, and **Linux Security**. I have transitioned from writing simple playbooks to building modular **Ansible Roles** to automate web server deployments.

🛠 Project Overview
-------------------

In this project, I automated the deployment of an Apache Web Server on **Oracle Cloud Infrastructure (OCI)** using Ansible Roles. This setup demonstrates the power of Infrastructure as Code (IaC) by configuring remote worker nodes (Ubuntu/Oracle Linux) from a central control node.

🧠 Key Concepts Covered
-----------------------

-   **Ansible Roles:** Organized tasks, templates, and variables into a reusable structure using `ansible-galaxy`.

-   **Jinja2 Templating:** Created dynamic `index.html.j2` files to display server-specific data like IP addresses.

-   **Cloud Networking:** Configured **Ingress Rules** in Oracle Cloud VCN to allow traffic on Port 80.

-   **Linux Security (iptables):** Managed host-level firewalls to permit HTTP traffic.

-   **Privilege Escalation:** Managed root-level tasks using `become: yes` and `--ask-become-pass`.

* * * * *

📂 Role Structure
-----------------

Bash

```
apache_web/
├── defaults/    # Default variables (e.g., port: 80)
├── handlers/    # Service restart triggers
├── tasks/       # Main automation logic (apt, service, template)
├── templates/   # Dynamic index.html.j2
└── vars/        # High-priority variables

```

* * * * *

🚀 How to Run the Playbook
--------------------------

### 1\. Prerequisites

-   Ansible installed on the Control Node.

-   SSH access to Worker Nodes via Private Keys.

-   Port 80 opened in the Cloud Console (Security Groups).

### 2\. Execution

Run the following command from the project root:

Bash

```
ansible-playbook -i hosts site.yml --ask-become-pass

```

### 3\. Troubleshooting the Firewall

If the website is not accessible via the Public IP, ensure the internal Linux firewall is allowing traffic:

Bash

```
sudo iptables -I INPUT -p tcp --dport 80 -j ACCEPT

```

* * * * *

📈 Learning Progress
--------------------

-   [x] Setting up Inventory & SSH Keys.

-   [x] Writing basic Playbooks.

-   [x] Creating Modular Roles.

-   [x] Handling Templates & Variables.

-   [x] Cloud Firewall (OCI) vs. OS Firewall (iptables).

-   [ ] Implementing Handlers (Next Step).

* * * * *

👨‍💻 Author
------------

**Afsar** *Software Engineer | Aspiring DevOps Expert* *Working on Sanofi Pharma Project @ Cognizant*