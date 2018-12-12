# lookup Plugin 

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