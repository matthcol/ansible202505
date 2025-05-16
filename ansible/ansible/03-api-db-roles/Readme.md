## Init roles
ansible-galaxy init roles/common
ansible-galaxy init roles/api
ansible-galaxy init roles/db

## Play the playbook
ansible-playbook -u deployer -i hosts playbook-install.yml 

Verbose mode:
ansible-playbook -u deployer -i hosts -v playbook-install.yml 
ansible-playbook -u deployer -i hosts -vv playbook-install.yml 
ansible-playbook -u deployer -i hosts -vvv playbook-install.yml 

List tasks, tags, ...:
ansible-playbook --list-tasks -i hosts  playbook-install.yml

tags:
ansible-playbook -u deployer -t API -i hosts  playbook-install.yml
ansible-playbook -u deployer -t DB -i hosts  playbook-install.yml
ansible-playbook -u deployer -t DBG -i hosts  playbook-install.yml
ansible-playbook -u deployer --skip-tags DBG -i hosts  playbook-install.yml

start at task:
ansible-playbook -i hosts -u deployer --start-at-task "Create DB User" playbook-install.yml

## Test with Curl
### Host API
curl -G -L localhost:8000/movies

curl -L -X POST localhost:8000/movies \
  -H "Content-Type: application/json" \
  -d '{"title": "ET", "year": 1982, "duration": 120 }'

### Swagger
From an host with a graphical interface:
