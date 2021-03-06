# Ansible Playbooks
## Warehouse for Ansible Playbooks

This warehouse contains a list of playbooks based on OS, Application, and Signal Sciences playbook applicable to the module required. Each directory contains a specific set of playbooks based on OS and Application. Execute the playbooks in the following order:
            
## Setting up your server
The `[software]-[os]-deployment-playbook.yml` will provide you with a playbook to install the software applicable to your OS. For example: The `apache-centos-deployment-playbook.yml` will install Apache HTTP Server on a CentOS system in order to fulfill the prerequisites for installing the Signal Sciences agent and module.

## Installing SigSci agent/module
The `key.yml` file in the var directory is where the Signal Sciences agent keys are stored. The playbook `sigsci-[*app*]-deployment-playbook.yml` to install the agent/module applicable to the environment. Be sure to fill in the variables:
```
          agent_access_key: [enter SigSci agent access key here] 
          agent_secret_key: [enter SigSci agent secret key here]
```

## Host file
The host file is going to maintain the inventory. The host directory is located under the root of the ansible-playbooks directory. This hosts file uses INI format, but you can modify it to use YAML based on [Ansible Documentation](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#inventory-basics-formats-hosts-and-groups) 

```
[apache-servers]
server1   ansible_host=174.138.13.97    ansible_connection=ssh
server2   ansible_host=188.166.115.68   ansible_connection=ssh
server3   ansible_host=188.166.123.245  ansible_connection=winrm
```
