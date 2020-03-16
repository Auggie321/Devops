### vagrant的使用场景(待完善)  

>* mac下不用点击虚拟机图标图标，terminal下即可轻松快速，创建虚机
>* win下不用在使用vmware workstation去克隆，安装，手动点击配置即可快速准备实验vm
>* 编排化创建本地虚机资源并能快速测试使用
>* 生产和测试环境一致，这点上随着docker的发展，vagrant的影响正在转移
>* 针对批量快速创建服务器，不涉及单独硬盘的挂载设置，vagrant+virtualbox首选；需要单独挂载硬盘，建议使用vmware克隆配合shell和ansible；  


### vagrant使用感受  
```
虽然docker盛行，但是底层vm的一些环境的特殊性，docker还是无法取代vm.
容器的发展，加速了编排化在生产部署的应用.传统界面vmware workstation和virtualbox在GUI界面下创建和克隆设置虚机，效率极其的低，尤其手头实验立马要用，重复劳动而又耗时的体验，真的有点难以忍受。由此vagrant，快速高效的编排创建虚机的特性，也正是他一直延续的原因之一吧
```


### vagrant缺点  
```
vagrant的编排有两部分组成（Vagrantfile和镜像），由于国内的网络问题，
镜像下载速度过慢的问题，目前我所知道的，并没有什么快速的proxy方案，只能手动http下载镜像或者torrent的形式单独下载镜像是在国内最快的  

痛点：
1.由于vagrant配合vmware workstation需要付费（key费用），针对vagrant+virtualbox使用比较常见；  
但是virtualbox本身的优化确实干不过vmware,vbox功能也不多；virtualbox新建磁盘速度非常慢；涉及硬盘挂载实验建议换用vmware环境  
2.win10上对于vagrant destory的优化不是很好,需要手动删除virtualbox  
```

### vagrant使用
```
写好Vagrantfile并下载好镜像后，即可手动打开

vagrant box add centos7 virtualbox.box 
//添加package.box，镜像命名为centos7

vagrant up
//开启vm

vagrant halt 
//关闭vm

vagrant status 
//确认当前虚拟机状态
```