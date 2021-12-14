# Install Mariadb

This role install and configure mariadb for selected instance.

## Role Variables

| Variable            | Required | Default       | Choices                   | Comments                               |
| ------------------- | -------- | ------------- | ------------------------- | -------------------------------------- |
| login_user          | yes      | root          |                           | Username to login with                 |
| mysql_root_password | yes      | j*LqpnwlC9pi  |                           | Password of the username to login with |
| dbname              | yes      | drupaldb      |                           | Name of the db to import               |
| host                | yes      | localhost     |                           | Target host for database and proxy     |


## Example Playbook

```yaml
- name: Install mariadb for selected instance
  hosts: new_node
  roles:
    - install.mariadb
  vars:
    - login_user: root
    - mysql_root_password: j*LqpnwlC9pi
    - dbname: drupaldb
    - host: localhost

```
## Author Information
Yigithan Saglam - saglamyigithan@gmail.com