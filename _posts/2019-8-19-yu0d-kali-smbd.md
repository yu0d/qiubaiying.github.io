
###kali��װ֮smbd

�������ļ���/etc/sabma/smb.conf

�������飺
comment---------ע��˵��

path------------������Դ������·�����ƣ�����·��Ҫ��ȷ�⣬Ŀ¼��Ȩ��ҲҪ���

browseable------��yes/��no�������Դ����ʾ����Ŀ¼����Ϊ�������ָ������·�����ܴ�ȡ

printable-------��yes/��no�����ӡ

hide dot ftles--��yes/��no���������ļ�

public----------��yes/��no����������Ϊ������������֤(ֻ�е�security = share ʱ�����������)

guest ok--------��yes/��no����������Ϊ������������֤(ֻ�е�security = share ʱ�����������)

read only-------��yes/��no��ֻ����ʽ������writable������ͻʱҲwritableΪ׼

writable--------��yes/��no����ֻ����ʽ������read only������ͻʱ������read only

vaild users-----�趨ֻ�д������ڵ��û����ܷ��ʹ�����Դ(�ܾ�����)(�û���/@����)

invalid users---�趨ֻ�д������ڵ��û����ܷ��ʹ�����Դ(�ܾ�����)(�û���/@����)


read list-------�趨�������ڵĳ�ԱΪֻ��(�û���/@����)

write list------���趨Ϊֻ��ʱ����ֻ�д��趨�������ڵĳ�Ա�ſ���д�붯��(�û���/@����)

create mask-----�����ļ�ʱ������Ȩ��

directory mask--����Ŀ¼ʱ������Ȩ��

force group-----ָ����ȡ��Դʱ���Դ��趨��Ⱥ��ʹ���߽�����ܴ�ȡ(�û���/@����)

force user------ָ����ȡ��Դʱ���Դ��趨��ʹ���߽�����ܴ�ȡ(�û���/@����)

allow hosts-----�趨ֻ�д�����/IP���û����ܷ��ʹ�����Դ

allwo hosts = ���� except IP

deny hosts------�趨ֻ�д�����/IP���û����ܷ��ʹ�����Դ

allow hosts=������ָ��IPָ��IP

deny hosts=ָ��IP������ָ��IP

####�ļ�ĩβ+:
```
[share]
    path=/share
	security=share
	public=no
	writable=yes
	browseable=yes
	writable
```
####������ʽ��/etc/init.d/smbd start|stop|status


##selinux ������