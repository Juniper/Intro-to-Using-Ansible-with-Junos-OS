# What is Ansible?
Ansible is an automation framework that is used for automating tasks. Ansible is mostly used to compute repetitive tasks. Ansible supports a wide range of integrations. The most commonly used ones are infrustructure, networks, containers, cloud, and devop tools. To learn more about Ansible and check out their [website](https://ansible.com). 

Juniper Networks specifically uses Ansible to automate network infrustructure. Although one might think that this is a daunting task, it is actually something anyone can do even without a strong programming background. In this guide, we will be showing how to use Ansible with Junos. 

Ansible is broken into
- python
- yaml
- jinga 
- playbooks

Ansible automation tasks are written in YAML (to see a brief overview of YAML file structure click [here](../master/resources/yaml.pdf)). We refer to these as playbooks. To automate the jobs, a user executes the playbook against a set of hosts listed in an inventory file. To read a short intro on playbooks click [here](../master/resources/playbooks.pdf).

We will be going over the following topics (for more details check out the [wiki](https://github.com/Juniper/ansible-junos-examples/wiki):
1. Juniper and Ansible
2. Technical use cases
3. Installing Ansible
4. Unitask playbooks

    i. [junos_install_config](https://github.com/Juniper/ansible-junos-examples/wiki/junos_install_config)
    
    ii. [junos_get_facts](https://github.com/Juniper/ansible-junos-examples/wiki/junos_get_facts)
    
    iii. [junos_commit](https://github.com/Juniper/ansible-junos-examples/wiki/junos_commit)




