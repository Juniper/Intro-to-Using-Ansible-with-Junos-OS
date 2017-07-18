# What is Ansible?
Ansible is an automation framework that is used for automating infrustructure tasks. Juniper Networks specifically uses it to automate network infrustructure. In this guide, we will be showing how to use Ansible with Junos. 

Ansible automation tasks are written in YAML (to see a brief overview of YAML file structure click [here](../master/resources/yaml.pdf)). We refer to these as playbooks. To automate the jobs, a user executes the playbook against a set of hosts listed in an inventory file. To read a short intro on playbooks click [here](../master/resources/playbooks.pdf).

We will be going over the following topics (for more details check out the [wiki](https://github.com/Juniper/ansible-junos-examples/wiki):
1. Juniper and Ansible
2. Technical use cases
3. Installing Ansible
4. Unitask playbooks
   * junos_install_config
   * junos_get_facts
   * junos_commit


We will now show how to install Ansible. 

# Steps to install Ansible
Prereqs:
1. Python 2.6 or 2.7
2. PyPi https://pypi.python.org/pypi

As root user enter 

sudo pip install ansible 

sudo ansible-galaxy install Juniper.junos on the command line. 

Next, we will show examples of playbooks for 3 different modules. 

# junos_install_config
- video
- code
- command line execution
- output
- explanation along the way or at the very end?

# junos_get_facts
insert video

The code below is a yaml file called to collect the facts from the junos device. 

To print the facts of the specific junos device, enter the following line in the command line:

ansible-playbook -i all.inv facts.pb.yaml 

when -i reads the following inventory file (in this case all.inv) that specifies the host information and facts.pb.yaml is the yaml code below.
```
---
- name: Get facts
  hosts: junos-all
  connection: local
  gather_facts: no
  roles:
    - Juniper.junos
  vars_prompt:
    - name: ADMUSER
      prompt: Username
      private: no
    - name: ADMPASS
      prompt: password
      private: yes
  tasks:
    - name: Get junos facts
      junos_get_facts:
        host: "{{ inventory_hostname }}"
        user: "{{ ADMUSER }}"
        passwd: "{{ ADMPASS }}"
      register: junos
    - name: Print facts
      debug:
        var: junos
```
The output of executing the command above is shown below:
```
TASK [Get junos facts] *********************************************************
ok: [10.164.1.92]

TASK [Print facts] *************************************************************
ok: [10.164.1.92] => {
    "junos": {
        "changed": false, 
        "facts": {
            "HOME": "/var/home/labadmin", 
            "RE0": {
                "last_reboot_reason": "Router rebooted after a normal shutdown.", 
                "model": "RE-MX80-48T", 
                "status": "OK", 
                "up_time": "8 days, 10 hours, 42 minutes, 8 seconds"
            }, 
            "domain": "englab.juniper.net", 
            "fqdn": "eabu-sol-eng-dc-s11.englab.juniper.net", 
            "has_2RE": false, 
            "hostname": "eabu-sol-eng-dc-s11", 
            "ifd_style": "CLASSIC", 
            "model": "MX80-48T", 
            "personality": "MX", 
            "serialnumber": "F9440", 
            "switch_style": "BRIDGE_DOMAIN", 
            "vc_capable": false, 
            "version": "15.1F5-S2.5", 
            "version_info": {
                "build": 5, 
                "major": [
                    15, 
                    1
                ], 
                "minor": "5-S2", 
                "type": "F"
            }
        }
    }
}

PLAY RECAP *********************************************************************
10.164.1.92                : ok=2    changed=0    unreachable=0    failed=0   
```
- explanation along the way or at the very end?

# junos_commit
- video

This modules performs a commit without changing the configuration file. 

To execute the commit, run the following line:

ansible-playbook -i all.inv commit.yaml

when all.inv is the inventory file and commit.yaml is the playbook. 
```
---
- name: Commit
  hosts: junos-all
  connection: local
  gather_facts: no
  roles:
    - Juniper.junos
  vars_prompt:
    - name: ADMUSER
      prompt: Username
      private: no
    - name: ADMPASS
      prompt: password
      private: yes
  tasks:
    - name: Confirm the commit
      junos_commit:
        host: "{{ inventory_hostname }}"
        user: "{{ ADMUSER }}"
        passwd: "{{ ADMPASS }}"
        comment: "commit confirmed
```
Output:
```
PLAY [Commit] ******************************************************************

TASK [Confirm the commit] ******************************************************
changed: [10.164.1.92]

PLAY RECAP *********************************************************************
10.164.1.92                : ok=1    changed=1    unreachable=0    failed=0   
```
If you connect to your device and execute the command: show system commit on the command line, you should see your commit in the list of commits.
