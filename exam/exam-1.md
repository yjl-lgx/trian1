## **�ڸ��˵���ʹ��vmware��װCentOS��Ubuntu�����**
�����ڰٶ����ҵ�vmware���ص��Լ����ԣ���������ʾ��װ���ڰٶ�������Ӧ�������Կ��ע�ἤ�
# һ ��װcentos7
- 1����������centos�����ҵ�CentOS-7����װ����
- 2����VMware Workstation ������˵����ļ���ѡ�ѡ���½����������
- 3��ѡ���Զ��壬Ȼ��ѡ���Լ���vmware�汾��
- 4��Ȼ��ѡ��λ�ò�ѡ���Ժ�װ;
- 5��ѡ��汾���Լ��ͷ�����ϵͳ��Ȼ��ѡ�������Լ���װλ�ã�
- 6���������������������������Ĭ�ϣ�
- 7���޸�������ڴ�Ϊ2G��
- 8��ѡ���������ͣ���ѡ��ʹ���Žӣ�
- 9������ͼ����  
![](1.png )  
![](2.png )  
![](3.png )  
![](4.png )  
![](5.png )  
- 10�� Ȼ�󴴽���� �����������������������´���  
![](6.png )  
![](7.png )  
![](8.png )  
- 11����������밲װ���棬ѡ��ϵͳ��װ��������� Enter�������  
![](9.png )  
- 12���ȴ���װ��ѡ�����ԣ�ѡ��  
![](10.png )  
- 13��Ȼ��ѡ����Ҫ�������װ  
![](picture\11.png )  
- 14��Ȼ���������ѡ����Сϵͳ������  
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
- 15�����ѡ����ܸ���  

# �� Ubuntu�İ�װ
- 1�����룺http://www.ubuntu.com  
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

# �� ��Centos7���þ�̬ip�Լ�ʹ��xshellԶ������Centos  
- 1�����Ȳ鿴��������������״̬��ʹ���������� 
<table><tr><td bgcolor=#7F>
<font color=white size=2 face=�����塱>$ systemctl status NetworkManager.service</font> 
</td></tr></table> 
- 2���ٲ鿴ʹ�õ����Ǹ�����ӿ�  
<table><tr><td bgcolor=#7F>
<font color=white size=2 face=�����塱>$ nmcli dev status</font> 
</td></tr></table> 
![](50.png )  
- ���ĳ���ӿڵ�nmcli���������ǡ�connected�����籾���е�ens33����  
- �����˵�ýӿ���������������������Ϊ������һ����̬IP��ַ��  
- 3����/etc/sysconfig/network-scriptsĿ¼���ҵ��ýӿڵ������ļ���ifcfg-ens33�����Լ��Ľӿڣ���  
<table><td bgcolor=#7F>
<font color=white size=2 face=�����塱>$ vi /etc/sysconfig/network-scripts/ifcfg-ens33</font>
</td></table>
- 4���򿪺��޸�����  
<table><td bgcolor=#7F>
<font color=white size=2 face=�����塱>$ vi /etc/sysconfig/network-scripts/ifcfg-ens33 </font>  
<font color=white size=2 face=�����塱>BOOTPROTO="static" #dhcp��Ϊstatic </font>  
<font color=white size=2 face=�����塱>ONBOOT="yes" #�������ñ����� </font>  
<font color=white size=2 face=�����塱>IPADDR=192.168.0.15 #��̬IP </font>  
<font color=white size=2 face=�����塱>GATEWAY=192.168.0.1 #Ĭ������ </font>  
<font color=white size=2 face=�����塱>NETMASK=255.255.255.0 #�������� </font>   
<font color=white size=2 face=�����塱>DNS1=114.114.114.114 #DNS ���� </font>
</td></table> 
- ��NM_CONTROLLED=no����ʾ�ýӿڽ�ͨ���������ļ��������ã�������ͨ��������������й���  
- ��ONBOOT=yes���������ǣ�ϵͳ��������ʱ�����ýӿڡ�  
- 5�������˳�����������  
<table><tr><td bgcolor=#7F>
- <font color=white size=2 face=�����塱>$ service network restart</font>
</td></tr></table>
- 6���鿴�Ķ����Ч����ip addr ����鿴������Ϣ  
![](51.png )  
  
# �� ��������������Xhellk����  
- 1����Xshell�½�һ�����ӣ���ͼ��  
![](52.png )   
- 2��������Centos�����õ�IP����ͼ��  
![](53.png )  
- 3�������û����Լ�����(centos)  
![](54.png )  
- 4��������->������֤һ���ǲ������������Լ���centos  
![](55.png )  
### End