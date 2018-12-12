# Lookup Plugin 

- List of Plugins: `ansible-doc -t lookup -l`
- Doc to Plugin: `ansible-doc -t lookup [PluginNmae]` -> `ansible-doc -t lookup k8s`

### Example:
```yaml
---

- hosts: local
  vars:
    ns: "{{ lookup('k8s', api_version='v1', kind='Namespace') }}"

  tasks:
    - name: Namespaces
      debug:
        msg: "{{ item.metadata.name }}"
      with_items: "{{ ns }}"
```     

# Jinja-Example

## Lists (Filter, Map)

```yaml
---

- hosts: local
  gather_facts: no
  vars:
    mylist: [ barfoo.yml, foobar.txt, foo.yml, bar.doc ]

  tasks:
    - name: Print List
      debug: msg="{{ mylist }}"

    - name: Select yml from list
      debug: msg="{{ mylist | select('search','.yml') | list  }}"

    - name: Set result to var
      set_fact:
        result_list: "{{ mylist | select('search','.yml') | list | map('upper') | join(', ')  }}"

    - name: Print var result_list
      debug:
        msg: "Var result_list: {{ result_list }}"
```
