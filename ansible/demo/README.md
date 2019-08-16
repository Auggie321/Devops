```
Ansible is written by python. Some of its modules not support Python3, 
and some packages must python3 ansible could install, therefore, 
we need keep multiple python version with ansible to handle dev issues. 
```

### Multiple ansible-python env build
You could create three test servers with Vagrantfile for testing.

|vagrant tag  | server name | ip          |
|-------------|------------:| :---:       |
|    tmp1     |  master     | 192.168.60.7|
|    tmp2     |  node1      | 192.168.60.8|
|    tmp3     |  node2      | 192.168.60.9|


```
If you do not know vagrant, you could build three test servers in vm.

Master  
Func:install py3.7.2 in all nodes from master node

1>wget https://releases.ansible.com/ansible/rpm/release/epel-7-x86_64/ansible-2.8.3-1.el7.ans.noarch.rpm
2>rpm -Uivh ansible-2.8.3-1.el7.ans.noarch.rpm
3>cd /etc/ansible
4>ansible-playbook -i inventory/inventory playbooks/multi_py.yml
5>ansible -i inventory/inventory all -m shell -a  "python3 -V"    

Next:
if you want to keep multiple python ansible env, then i recommend you consider about virtualenv,
creating venv3 and pip install ansible,
keep ansible tools in sandbox far from way system contamination.
```
