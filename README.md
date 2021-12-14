# Setup Drupal and CiviCRM with Ansible
This project has been created and developed with Ansible in order to accelerate building process of the CiviCRM and set a standard in the installation process.
This project makes building Drupal development environments quick and easy, and introduces developers to the wonderful world of Drupal development on virtual machines.

## Requirements

Drupal is a PHP-based application that is meant to run behind a typical LAMP/LEMP/LEPP/etc. stack, so you'll need at least the following:

This role installs the following on an Ubuntu 20.04 (by default) linux VM:

 - Apache (or Nginx)
 - PHP (version 7.2)
 - MariaDB
 - Drupal 8
 - CiviCRM,selected version,(default 5.44.0)
 
## Proxies

Configuration works with multiple operating systems and with multiple webservers. You can switch between Apache and Nginx (depending on which server you prefer) with ease. Apache is the webserver used out of the box.

## Example Playbook

```yaml

- name: Deploy Server
  hosts: localhost
  become: false
  gather_facts: false
  roles:
    -  role: server.deploy
  vars:
    - image_id: ""         
    - hostname: "" 
    - server_name: "" 
    - network: ""
    - datacenter_node: ""
    - type: "small"
    - leo_url: 
    - user_token: ""
  environment:
    ANSIBLE_HOST_KEY_CHECKING: false

- name: Install drupal+civicrm+apache+php+mariadb
  hosts: newnode
  become: false
  gather_facts: yes
  roles:
    -  role: install.apache
    -  role: install.mariadb
    -  role: install.php
    -  role: install.drupal
    -  role: install.civicrm
  vars:
    - proxy: apache
    - domain: drupal.ahmetfd.com
    - login_user: drupal_user
    - login_password: 
    - user_name: root
    - user_password: 
    - mysql_root_password: 
    - dbname: drupaldb
    - host: localhost
  environment:
    ANSIBLE_HOST_KEY_CHECKING: false

```
## Author Information
Yigithan Saglam - saglamyigithan@gmail.com
