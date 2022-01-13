---
- name: Variables
  hosts: all
  become: true
  gather_facts: no
  vars:
    users:
      - Ramesh
      - Suresh
    folders:
      - providers
      - projects

  tasks:
    - name: Ensure user exists
      user:
         name: '{{ item }}'
      with_items:
        - '{{ users }}'

    - name: Ensure Folder exists
      file:
        path: '/home/{{ item.0 }}/{{ item.1 }}'
        state: directory
      with_nested:
      - '{{ users }}'
      - '{{ folders }}'

