# Playbook to install a deployer user

## 1 - Generate SSH key

 ssh-keygen
 - /home/srvadmin/.ssh/id_rsa_deploy.pub
 - + passphrase


## 2 - Create User : sudoers + copy SSH Key
ansible-playbook -u srvadmin -k -K -i hosts playbook-deployuser.yml

## 3 - Unlock SSH Key wwith passphrase
### start agent
ssh-agent  => copy paste output
### add key to agent
ssh-add ~/.ssh/id_rsa_deploy
### checkup
ssh-add -l
### remove keys
ssh-add -D

## Play again with new user
ansible-playbook -u deployer -e "user_deploy=deployer2" -i hosts playbook-deployuser.yml
ansible-playbook -u deployer -e "user_deploy=deployer2" -i hosts playbook-deactivateuser.yml