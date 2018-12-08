# ansible-examples
examples for ansible

# add hoc command
`ansible -m ping all`

`ansible -m shell -a 'echo Hello Ansible' all`

# run example playbooks
- simple playbook (without role): `ansible-playbook simple-playbook.yml`
- echo example: `ansible-playbook echo-playbook.yml`
- create kafka in virtual box: `ansible-playbook kafka-playbook.yml`
- openshift example: `ansible-playbook openshift-playbook.yml`
- 