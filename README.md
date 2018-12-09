# Ansible-examples

## add hoc command
`ansible -m ping all`

`ansible -m shell -a 'echo Hello Ansible' all`

## run example (no playbook)
- simple playbook (without role): `ansible-playbook simple-playbook.yml`

## run example playbooks
- echo example: `ansible-playbook echo-playbook.yml` or `ansible-playbook echo-playbook.yml --extra-vars "var_host=kafka"`
- create kafka in virtual box: `ansible-playbook kafka-playbook.yml`
- openshift example: `ansible-playbook openshift-playbook.yml`

# Ansible hints

## get ansible facts (variables like: ansible_distribution)
`ansible -m setup localhost`