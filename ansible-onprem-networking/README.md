**Ansible Framework Overview for On-Premises Networking**
<img width="808" height="826" alt="image" src="https://github.com/user-attachments/assets/34e4159f-9753-43b5-8e9d-ea3c0976675a" />

**Key Practical Points**
- TCP/IP Configuration: Use Ansible modules or command tasks to set static IP addresses, subnet masks, and gateways on Linux/Unix servers or network devices via templates like interface.conf.j2.

- DNS Setup: Automate updating system DNS resolvers (e.g., /etc/resolv.conf) or configure DNS servers to ensure proper name resolution.

- Subnet & VLAN: Automate VLAN tagging and subnet assignments on switches or routers to segment network traffic logically.

- Firewalls: Configure firewall rules programmatically (iptables or nftables) ensuring the allowed/blocked TCP/IP ports and protocols for services.

- VPN Tunnels: Use Ansible to deploy or update VPN configs (like OpenVPN or IPsec), enabling secure encrypted communication between on-prem sites.

- Handlers: Handlers restart or reload network, firewall, or VPN services upon config changes to apply settings immediately.

This framework provides idempotent, repeatable network setup for on-prem physical or virtual infrastructure using Ansible automation, supporting complex networking scenarios with TCP/IP, DNS, VPC-like subnetting, security with firewalls, and secure VPN connectivity. It enhances network configuration reliability, ease of management, and fast rollout of changes.

**To create the on-premises infrastructure using the Ansible code framework provided earlier, follow these command steps:**

1. Ensure Ansible is installed

   **$ansible --version**

2. Prepare your Ansible inventory and variables

   -Inventory file (inventories/hosts.ini) should list your target hosts.
   -Variables defined in group_vars/all.yml must reflect your infrastructure network settings.

3. Run the Ansible playbook

   Navigate to the directory with playbook.yml, then execute:

   **$ansible-playbook -i inventories/hosts.ini playbook.yml**

4. Verify tasks completion

   Watch for any errors in output; Ansible run will configure TCP/IP, DNS, firewall, and VPN settings on target hosts.

5. Optional: Run ad-hoc commands to check connectivity

   **$ansible -i inventories/hosts.ini all -m ping**
   
   **$ansible -i inventories/hosts.ini all -a "ip addr show"**
   
   **$ansible -i inventories/hosts.ini all -a "iptables -L"**
   
This will deploy the configurations idempotently, setting up your on-premises servers with the desired networking components efficiently.
   
   
   

   
