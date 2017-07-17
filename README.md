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
- video
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
- command line execution
- output
- explanation along the way or at the very end?

# junos_commit
- video
- code
- command line execution
- output
- explanation along the way or at the very end?
