### 安装
[ansible rpm download][1]
```
截止到2019.08.05, centos初始默认的仓库ansible版本比较低为2.4版本, 很多高级的功能比如loop模块等无法使用,
需要自行安装高级的稳定版本.如果已经使用yum安装,可以安装rpm包，系统会自动更新, 并剔除旧有版本,
同时不影响现有ansible使用.生产ansible请谨慎.

centos7 install ansible2.8
wegt https://releases.ansible.com/ansible/rpm/release/epel-7-x86_64/ansible-2.8.3-1.el7.ans.noarch.rpm
rpm -Uivh ansible-2.8.3-1.el7.ans.noarch.rpm
ansible --version
```

### ansible-demo基础架构（processing）  
```
etc_ansible/
├── ansible.cfg
├── inventory
│   ├── group_vars
│   └── inventory
├── library
├── module_utils
├── playbooks
│   └── multi_py.yml
├── roles
├── scripts
└── vagrant
    └── Vagrantfile
```
```
ansible结合业务, 对架构的嵌套整合, 弱化了playbooks目录下bookyaml的集中配置,  
加重了架构间变量传导,依赖和执行,分离playbook的配置文件, include到具体的文件夹内部进行执行,  
对后续的维护和拓展大有帮助, 个人认为用好变量的传递是ansible的核心, 架构设计是最好的实践.  
```

### ansible production demo(processing)
```
随着业务复杂度的深入，ansible的使用也更多的偏向架构的调整和设计，  
给业务逻辑一个合适的ansible架构将是我后续更新的重点
```

### 文档
[ansible for devops][2],[github][6]  
[ansible汉化基础文档][3]  
[ansible-en-doc][4]  
[ansible-zh-doc][5]

[1]: https://releases.ansible.com/ansible/rpm/release/epel-7-x86_64/
[2]: https://www.ansible.com/resources/ebooks/ansible-for-devops
[3]: http://getansible.com/
[4]: https://docs.ansible.com/ansible/latest/
[5]: https://ansible-tran.readthedocs.io/en/latest/docs/
[6]: https://github.com/geerlingguy/ansible-for-devops
