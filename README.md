# What is Ansible?
Ansible is an automation framework that is used for automating tasks. Ansible supports a wide range of integrations. The most commonly used ones are infrustructure, networks, containers, cloud, and devop tools. To learn more about Ansible check out their [website](https://ansible.com). 

# Why use Ansible?
Ansible is a great tool if you need to make changes and/or execute specific tasks on more than one device. Instead of having to do a specific task on multiple machines one at a time, you can do that task on all of them at once by executing one script (playbook). Also, if you have multiple tasks you can combine them into one playbook. This saves a lot of time for the developer and minimizes the chance of any errors. 

# Ansible and Junos OS
[Juniper Networks](http://www.juniper.net/us/en/) specifically uses Ansible to automate network infrustructure. Although one might think that this is a daunting task, it is actually something anyone can do even without a strong programming background. In this guide, we will be showing how to use Ansible with Junos. 

Although Ansible is written in Python, knowing Python is not necessary to use Ansible because the automation tasks are written in the human readable language YAML. Click [here](../master/resources/yaml.pdf) to get a brief introduction to YAML. These YAML files are called playbooks. Users execute the playbook against a set of hosts in an inventory file to automate the job. To read a short intro on playbooks click [here](../master/resources/playbooks.pdf). Playbooks also make use of the Jinja2 templating system. All these tools together make Ansible a very easy to use, dynamic tool for automating jobs.  

# Ansible's Interoperability
Ansible can be used with other vendors and/or software as well. Some include: 
* Network vendors: Arista, Cisco, Cumulus, Nokia 
* Cloud technologies: Amazon Web Server, OpenStack, VMWare
* Operating Systems: Ubuntu, Red Hat Enterprise Linux

# [Wiki Contents](https://github.com/Juniper/ansible-junos-examples/wiki)
1. Juniper and Ansible
2. Technical use cases
3. Installing Ansible
4. Playbooks

    i. Initial Installation - install a configuration on any Junos OS device via console
     * [Code](https://github.com/Juniper/ansible-junos-examples/blob/master/library/junos_install_config.yaml)
     * [Read the doc](https://github.com/Juniper/Intro-to-Using-Ansible-with-Junos-OS/wiki/Initial-Installation)
     * [Watch the video](https://www.youtube.com/watch?v=gHFyhr3imIc)
     * [Other Variation](https://github.com/ksator/ansible-training-for-junos-automation/blob/master/junos_install_conf/pb.yml)
     
    ii. Health Checks - get some facts about your device like the serial number, hostname, and more
      * [Code](https://github.com/Juniper/ansible-junos-examples/blob/master/library/junos_get_facts.yaml)
      * [Read the doc](https://github.com/Juniper/Intro-to-Using-Ansible-with-Junos-OS/wiki/Health-Checks)
      * [Watch the video](https://www.youtube.com/watch?v=KDPTs_9qd8o) 
      * [Other Variation](https://github.com/ksator/ansible-training-for-junos-automation/tree/master/junos_get_facts/pb.yaml)
      
    iii. Provisioning - add two lines to the existing configuration and save the changes
      * [Code](https://github.com/Juniper/ansible-junos-examples/blob/master/library/junos_commit.yaml)
      * [Read the doc](https://github.com/Juniper/Intro-to-Using-Ansible-with-Junos-OS/wiki/Provisioning)
      * [Watch the video](https://www.youtube.com/watch?v=M4qSlrb3-zU)
      * [Other Variation](https://github.com/ksator/ansible-training-for-junos-automation/blob/master/junos_commit/pb.yml)

# License
Apache 2.0

# Contributors
Noa Shadmon, Jessica Garrison


