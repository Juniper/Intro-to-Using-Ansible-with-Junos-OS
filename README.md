# What is Ansible?
Ansible is an automation framework that is used for automating tasks. Ansible supports a wide range of integrations. The most commonly used ones are infrustructure, networks, containers, cloud, and devop tools. To learn more about Ansible check out their [website](https://ansible.com). 

Juniper Networks specifically uses Ansible to automate network infrustructure. Although one might think that this is a daunting task, it is actually something anyone can do even without a strong programming background. In this guide, we will be showing how to use Ansible with Junos. 

Although Ansible is written in Python, knowing Python is not necessary to use Ansible because the automation tasks are written in the human readable language YAML. Click [here](../master/resources/yaml.pdf) to get a brief introduction to YAML. These YAML files are called playbooks. Users execute the playbook against a set of hosts in an inventory file to automate the job. To read a short intro on playbooks click [here](../master/resources/playbooks.pdf). Playbooks also make use of the Jinja2 templating system. All these tools together make Ansible a very easy to use, dynamic tool for automating jobs.  

We will be going over the following topics (for more details check out the [wiki](https://github.com/Juniper/ansible-junos-examples/wiki)):
1. Juniper and Ansible
2. Technical use cases
3. Installing Ansible
4. Playbooks

    i. [junos_install_config](https://github.com/Juniper/ansible-junos-examples/wiki/junos_install_config)
    
    ii. [junos_get_facts](https://github.com/Juniper/ansible-junos-examples/wiki/junos_get_facts)
    
    iii. [junos_commit](https://github.com/Juniper/ansible-junos-examples/wiki/junos_commit)




