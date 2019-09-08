```
---
- hosts: web
  become: yes
  tasks:
  - name: Installing httpd service
    yum:
     name: httpd
     state: latest
  - name: creating index.html
    file:
     path: /var/www/html/index.html
     state: touch
  - name: inserting host name in index.html
    lineinfile:
     path: /var/www/html/index.html
     line: "{{ ansible_host }}"   
```




