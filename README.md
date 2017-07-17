# ansible-junos-examples
Examples of Using Ansible with Junos Devices

Link: What is Ansible and how is it used
Link: Overview of different file types/examples/what they look like - yaml, pb, etc

# junos_install_config
- video
- code
- command line execution
- output
- explanation along the way or at the very end?

# junos_get_facts
- video ⋅⋅
The code below is a yaml file called to collect the facts from the junos device. 
⋅⋅To print the facts of the specific junos device, enter the following line in the command line:
⋅⋅ansible-playbook -i all.inv facts.pb.yaml 
- when -i reads the following inventory file (in this case all.inv) that specifies the host information 
- facts.pb.yaml is the yaml code below.
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
- code
- command line execution
- output
- explanation along the way or at the very end?
