# Install Apache

This role install Apache for selected instance.

## Role Variables

| Variable        | Required | Default                    | Choices                   | Comments                               |
| --------------- | -------- | -------------------------- | ------------------------- | -------------------------------------- |
| domain          | yes      | http://drupal.ahmetfd.com  |                           | Domain address of preferred website    |
| proxy           | yes      | apache                     | nginx                     | Name of reverse proxy.                 |

## Example Playbook

```yaml
name: Install Apache
  hosts: newnode
  roles:
    - install.apache
  vars:
    - proxy: apache
    - domain: j*LqpnwlC9pi

```
## Author Information
Yigithan Saglam - saglamyigithan@gmail.com