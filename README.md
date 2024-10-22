Ansible Role: create_user
=========

Creates a user and places it in the specified group. Adds your local public ssh key for passwordless access

Role Variables
--------------

    user_name: #enter name of the new user (required)
    user_group: #enter name of the new group (required)
    task: install <- default value (have default value)
    path_to_local_key: #enter FULL PATH to your local id_rsa.pub file (required)

Example Playbook
----------------

    ---
    - hosts: all
      become: yes
      vars_files:
        - vars/main.yml

      roles:
        - { role: zh2s.create_user }

*Inside `vars/main.yml`*
-------

    path_to_local_key: /Users/yourLocalUsername/.ssh/id_rsa.pub
    user_name: newUser
    user_group: newGroup
