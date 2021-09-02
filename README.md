Install Wordpress on Ubuntu and RedHat
=========

This playbook installs Wordpress on Ubuntu and RedHat and creates users, and groups with admin privilege.

This is a test playbook for practice.

Requirements
------------

Required Core Files:
  - apache2
  - mysql-server 
  - python3-pymysql
  - php
  - php-mysql
  - libapache2-mod-php 

Role Variables
--------------

`mysql_root_password:` Set your custom root password"
`mysql_db:` "Set your database nameordpress"
`mysql_user:` "Set your mysql user name"
`mysql_password:` "Set the password for mysql user"



Example Playbook
----------------

This is an example on how to run all three roles with the playbook:

    ```yaml
    - name: Run roles playbook
      hosts: all
      become: true
      become_method: sudo
      roles:
        - { role: wordpress-ubuntu, when: ansible_os_family == 'Debian' }
        - { role: create-user-groups, when: ansible_os_family == 'Debian' }
        - { role: wordpress-redhat, when: ansible_os_family == 'RedHat' }
        ```

License
-------

BSD

Author Information
------------------

Role created for practice.
