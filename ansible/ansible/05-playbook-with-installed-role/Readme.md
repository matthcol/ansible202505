# Playbook with pre-installed role

## Prerequis
Role learning.apipython du projet 04-role-api

## Install role
Install manually or with playbook locally: playbook-installrole.yml

Manually:
```
ansible-galaxy role install -r requirements.yml
ansible-galaxy role install -r requirements.yml --roles-path ./roles
```

With a playbook:
```
ansible-playbook playbook-installrole.yml
```


## Use role in a playbook
In playbook playbook-installapidb.yml:
```
- name: Install API
  hosts: api
  roles:
    - learning.pythonapi 
```

Run playbook using role:
```
ansible-playbook -i hosts -u deployer playbook-installapidb.yml
```



