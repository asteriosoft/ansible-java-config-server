java-config-server
=========

Role for java sprint config-server deployment from artifactory or local fs. Vault backend can be configured optionally.

Role Variables
--------------

To do

Example Playbook
----------------
```
- hosts: servers
  become: yes
  gather_facts: yes

  vars:
    java_app_home_dir: "/opt/test/config-server"
    java_app_port: "8010"
    java_app_xmx: "1024m"
    java_app_xms: "512m"
    java_app_wait_for_port_open: true
    java_app_ssh_files_dir: "{{ playbook_dir }}/../ssh-files"
    java_app_vault:
      host: "vault"
      authentication: 
        aws_iam:
          iam_role: "iam-role"

  roles:
    - java-config-server
```

