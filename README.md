# Ansible example repo

[Getting Started — Ansible Documentation]( https://docs.ansible.com/ansible/2.6/user_guide/intro_getting_started.html )

## how to run at localhost
```
ansible localhost -m ping -k
```

[ansible — Ansible Documentation]( https://docs.ansible.com/ansible/2.6/cli/ansible.html )
* `-k`:ask target host ssh password without `IdentityFile`?
* `-u`:user (default value is same as now user)
* `-a`:run a live command(`-a "/bin/echo hello"`)
* `-b`:run as root by sudo
  * `-K`:ask sudo password
* `-e 'ansible_python_interpreter="/usr/bin/env python"'`: choose python which ansible use
* `-vvv`:verbose log

## how to run playbook

### run at localhost
```
ansible-playbook -i localhost-hosts -c local ping.yaml
```

### run at remote host
```
ansible-playbook -i remote-hosts -k -K ping.yaml
```

----

## FYI
### directory best practice
* [Best Practices — Ansible Documentation]( https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#directory-layout )

### 冪等性(idempotence)
* [AnsibleのScriptモジュールで冪等性をいい感じに担保したい \- Qiita]( https://qiita.com/Gustav/items/cbc937cfdfb1ba6efd42 )
* [Ansibleの冪等性とPlaybook ｜ Developers\.IO]( https://dev.classmethod.jp/server-side/ansible/ansible_playbook_with_idempotence/ )
