## module ping
ansible -i hosts -u srvadmin -k -m ping all
ansible -i hosts2 -u srvadmin -k -m ping all

NB: https://docs.ansible.com/ansible/latest/reference_appendices/interpreter_discovery.html

## module file
ansible -i hosts2 -u srvadmin -k -m file -a "path=/tmp/deploy state=directory" api      => CHANGED
ansible -i hosts2 -u srvadmin -k -m file -a "path=/tmp/deploy state=directory" api      => SUCCESS

ansible -i hosts2 -u srvadmin -k -m file -a "path=/opt/deploy state=directory" api      => FAILED (permission denied)

become: sudo (default)

ansible -i hosts2 -u srvadmin -k -b -K -m file -a "path=/opt/deploy state=directory" api