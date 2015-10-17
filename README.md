# Ansible Role: Creates ELB

Creates one or more ELBs in an AWS account.  This role also installs the AWSCLI to properly configure the ELB.

## Installation

``` bash
$ ansible-galaxy install https://github.com/crushlovely/ansible-elb.git
```
## Variables

You will want to fill all these in before running the role.

``` yaml
app_name: test
server_env: qa
access_key: ""
secret_key: ""
```
You can also add a vars folder to your project folder and have your variables served by adding them to a file and calling it in your playbook.

```yaml
- hosts: localhost
...
  vars_files:
    - vars/default_vars.yml
...
```
## Usage

Once this role is installed on your system, include it in the roles list of your playbook.

``` yaml
- hosts: localhost
  connection: local
  gather_facts: True
  roles:
    - ansible-elb
```

## Dependencies

None

## License

MIT
