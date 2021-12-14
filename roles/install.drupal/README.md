# Install Drupal

This role install all Drupal files, create Drupal database and Drupal database user.

## Role Variables

| Variable        | Required | Default       | Choices                   | Comments                               |
| --------------- | -------- | ------------- | ------------------------- | -------------------------------------- |
| user_name       | yes      | root          |                           | Username to login with                 |
| user_password   | yes      | j*LqpnwlC9pi  |                           | Password of the username to login with |
| dbname          | yes      | drupaldb      |                           | Name of the db to import               |
| host            | yes      | localhost     |                           | Target host for database and proxy     |
| proxy           | yes      | apache        | nginx                     | Name of reverse proxy.                 |
| domain          | yes      |               |                           | Domain address of preferred website    |

## Example Playbook

```yaml
- name: Install Drupal
  hosts: newnode
  roles:
    -  role: install.drupal
  vars:
    - domain: drupal.ahmetfd.com
    - user_name: root
    - user_password: j*LqpnwlC9pi
    - dbname: drupaldb
    - host: localhost
    - proxy: apache

```
## Author Information
Yigithan Saglam - saglamyigithan@gmail.com