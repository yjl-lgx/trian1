## **在个人电脑使用vmware安装CentOS和Ubuntu虚拟机**
首先在百度上找到vmware下载到自己电脑，并按照提示安装，在百度搜索对应的许可密钥，注册激活。
# 一 安装centos7
- 1：接下来在centos官网找到CentOS-7镜像安装包；
- 2：打开VMware Workstation ，点击菜单“文件”选项，选择”新建虚拟机”；
- 3：选择自定义，然后选择自己的vmware版本；
- 4：然后选择位置并选择稍后安装;
- 5：选择版本，以及客服操着系统，然后选择名字以及安装位置；
- 6：设置虚拟机处理器数量，可以默认；
- 7：修改虚拟机内存为2G；
- 8：选择网络类型，我选择使用桥接；
- 9：如下图操作  
![](1.png )  
![](2.png )  
![](3.png )  
![](4.png )  
![](5.png )  
- 10： 然后创建完成 点击开启虚拟机（若出现以下错误）  
![](6.png )  
![](7.png )  
![](8.png )  
- 11：开启后进入安装界面，选择系统安装，点击键盘 Enter键后继续  
![](9.png )  
- 12：等待安装后选择语言，选择  
![](10.png )  
- 13：然后选择需要的软件安装  
![](picture\11.png )  
- 14：然后进行配置选择最小系统的配置  
![](12.png )  
![](13.png )  
![](14.png )  
![](15.png )  
![](16.png )  
![](17.png )  
![](18.png )  
![](19.png )  
![](20.png )  
![](21.png )  
![](22.png )  
![](23.png )  
![](24.png )  
![](25.png )  
![](26.png )  
![](27.png )  
![](28.png )  
![](29.png )  
- 15：最后选择接受更改  

# 二 Ubuntu的安装
- 1：进入：http://www.ubuntu.com  
![](30.png )  
![](31.png )  
![](32.png )  
![](33.png )  
![](34.png )  
![](35.png )  
![](36.png )  
![](37.png )  
![](38.png )  
![](39.png )  
![](40.png )  
![](41.png )  
![](42.png )  
![](43.png )  

# 三 给Centos7配置静态ip以及使用xshell远程连接Centos  
- 1：首先查看网络管理器服务的状态：使用以下命令 
- $ systemctl status NetworkManager.service  
- 2：再查看使用的是那个网络接口  
![](50.png )  <br>
<table><tr><td bgcolor=#00>
<font color=white size=2 face=“黑体”>$ nmcli dev status</font> 
</td></tr></table>  
- 如果某个接口的nmcli的输出结果是“connected”（如本例中的ens33），  
- 这就是说该接口受网络管理器管理。你可以为它配置一个静态IP地址。  
- 3：进入/etc/sysconfig/network-scripts目录，找到该接口的配置文件（ifcfg-ens33这是自己的接口）。  
<table><td bgcolor=#7F>
<font color=white size=2 face=“黑体”>$ vi /etc/sysconfig/network-scripts/ifcfg-ens33</font>
</td></table>
- 4：打开后修改如下  
<pre><table><td bgcolor=#00> <font color=white size=2 >
/etc/sysconfig/network-scripts/ifcfg-ens33 <br> 
BOOTPROTO="static" #dhcp改为static  <br>
ONBOOT="yes" #开机启用本配置  <br>
IPADDR=192.168.0.15 #静态IP   <br>
GATEWAY=192.168.0.1 #默认网关  <br>
NETMASK=255.255.255.0 #子网掩码   <br>
NS1=114.114.114.114 #DNS 配置 <br>
</td></table></pre>
- “NM_CONTROLLED=no”表示该接口将通过该配置文件进行设置，而不是通过网络管理器进行管理。  
- “ONBOOT=yes”告诉我们，系统将在启动时开启该接口。  
- 5：保存退出后重启网络  
<table><td bgcolor=#7F>
<font color=white size=2 face=“黑体”>$ service network restart</font>
</td></table>
- 6：查看改动后的效果，ip addr 命令查看网络IP是否是192.168.0.15进行验证
 
# 四 配置完成下面进行Xhellk连接  
- 1：打开Xshell新建一个链接（如图）  
![](52.png )   
- 2：输入在Centos上配置的IP（如图）  
![](53.png )  
- 3：输入用户名以及密码(centos)  
![](54.png )  
- 4：点击完成->链接验证一下是不是链接上了自己的centos  
![](55.png )  
### End
