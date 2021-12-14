# Install CiviCRM

This role install CiviCRM for selected instance.

## Role Variables

| Variable        | Required | Default                    | Choices                   | Comments                               |
| --------------- | -------- | -------------------------- | ------------------------- | -------------------------------------- |
| civicrm_version | yes      | 5.44.0                     |                           | CiviCRM version                        |
| domain          | yes      | http://drupal.ahmetfd.com  |                           | Domain address of preferred website    |

## Example Playbook

```yaml
- name: Install CiviCRM
  hosts: newnode
  gather_facts: no
  roles:
    - install.civicrm
  vars:
    - civicrm_version: '5.44.0'
    - domain: 'http://drupal.ahmetfd.com'

```
## Author Information
Yigithan Saglam - saglamyigithan@gmail.com