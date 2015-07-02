# Ansible Role: Creates ELB Buckets

Creates one or more Elastic load balancers and configures them with a proxy protocol policy.  This role also installs the AWSCLI to properly configure the buckets

## Installation

``` bash
$ ansible-galaxy install https://github.com/crushlovely/ansible-elb.git
```
## Variables

You will want to fill all these in before running the role.

``` yaml
app_name: test
server_env: qa
aws_access_key: ""
aws_secret_key: ""
aws_elb:
  - port: 80
aws_vpc_subnets:
  - "\"subnet-xxxxxxx\""
  - "\"subnet-xxxxxxx\""
  - "\"subnet-xxxxxxx\""
  - "\"subnet-xxxxxxx\""
```
You can also add a vars folder to your project folder and have your variables served by adding them to a file and calling it in your playbook.

```yaml
- hosts: localhost
...
  vars_files:
    - vars/aws_vars.yml
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
