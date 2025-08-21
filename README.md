# ansible
---
- name: Install and Start Apache HTTPD
  hosts: all     # you can replace 'all' with a group like 'webservers'
  become: yes    # run as root

  tasks:
    - name: Install httpd package
      yum:
        name: httpd
        state: present

    - name: Ensure httpd is running and enabled
      service:
        name: httpd
        state: started
        enabled: yes

