# Ansible Collection - acch.collection_test

Testing collection structure - please ignore.

## Getting Started

Ansible 2.10 and above:

```shell
ansible-galaxy collection install git+https://github.com/acch/ansible-collection-test.git,master
```

Ansible 2.9:

```shell
git clone https://github.com/acch/ansible-collection-test.git collections/ansible_collections/acch/collection_test/
```

Sample playbook:

```yaml
# playbook.yml:
---
- hosts: all

  collections:
    - acch.collection_test

  pre_tasks:

    - name: Test connectivity
      ping:

  roles:
    - role1
    - role2
    - role3
```

Sample playbook run:

```shell
# ansible-playbook -i hosts playbook.yml

PLAY [all] ***********************************************************************************************

TASK [Gathering Facts] ***********************************************************************************
ok: [test01]

TASK [Test connectivity] *********************************************************************************
ok: [test01]

TASK [acch.collection_test.role1 : debug] ****************************************************************
ok: [test01] => {
    "msg": "Hello from role1"
}

TASK [acch.collection_test.role2 : debug] ****************************************************************
ok: [test01] => {
    "msg": "Hi from role2"
}

TASK [acch.collection_test.role3 : debug] ****************************************************************
ok: [test01] => {
    "msg": "Hey from role3"
}

PLAY RECAP ***********************************************************************************************
test01                     : ok=5    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```
