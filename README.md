# Ansible Role: Asterisk

[![Build Status](https://travis-ci.com/milad00ahmadi/ansible-role-asterisk.svg?branch=master)](https://travis-ci.com/milad00ahmadi/ansible-role-asterisk)

Installs and configures MySQL and Asterisk with ODBC realtime database driver.

Requirements
------------

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:


    - hosts: asterisk_machines
      roles:
        - role: milad00ahmadi.asterisk
          become: yes

Install via ansible-galaxy
--------------------------

Use ansible galaxy to download this role with:

    ansible-galaxy install milad00ahmadi.asterisk


## Dependencies

None.

## Example Playbook

    - hosts: asterisk_machines
      become: yes
      vars_files:
        - variables.yml
      roles:
        - { role: milad00ahmadi.asterisk }
        

*Inside `variables.yml`*:
        
    mysql_asterisk_user: user
    mysql_asterisk_user_password: password
    mysql_asterisk_database: asterisk
    mysql_asterisk_user_priv: "asterisk.*:ALL"
    mysql_root_password: password
    
    asterisk_user: asterisk
    asterisk_group: asterisk
    
    asterisk_config_path: ../../../files/asterisk/
    
    
  
## License

MIT / BSD
