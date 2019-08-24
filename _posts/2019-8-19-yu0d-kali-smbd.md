---
layout:     post
title:      smbd
subtitle:   smbd
date:       2019-08-19
author:     yu
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - smbd
    - 
---

>**smbd** 

###kali安装之smbd

主配置文件：/etc/sabma/smb.conf

参数详情：
comment---------注释说明

path------------分享资源的完整路径名称，除了路径要正确外，目录的权限也要设对

browseable------是yes/否no在浏览资源中显示共享目录，若为否则必须指定共享路径才能存取

printable-------是yes/否no允许打印

hide dot ftles--是yes/否no隐藏隐藏文件

public----------是yes/否no公开共享，若为否则进行身份验证(只有当security = share 时此项才起作用)

guest ok--------是yes/否no公开共享，若为否则进行身份验证(只有当security = share 时此项才起作用)

read only-------是yes/否no以只读方式共享当与writable发生冲突时也writable为准

writable--------是yes/否no不以只读方式共享当与read only发生冲突时，无视read only

vaild users-----设定只有此名单内的用户才能访问共享资源(拒绝优先)(用户名/@组名)

invalid users---设定只有此名单内的用户不能访问共享资源(拒绝优先)(用户名/@组名)


read list-------设定此名单内的成员为只读(用户名/@组名)

write list------若设定为只读时，则只有此设定的名单内的成员才可作写入动作(用户名/@组名)

create mask-----建立文件时所给的权限

directory mask--建立目录时所给的权限

force group-----指定存取资源时须以此设定的群组使用者进入才能存取(用户名/@组名)

force user------指定存取资源时须以此设定的使用者进入才能存取(用户名/@组名)

allow hosts-----设定只有此网段/IP的用户才能访问共享资源

allwo hosts = 网段 except IP

deny hosts------设定只有此网段/IP的用户不能访问共享资源

allow hosts=本网段指定IP指定IP

deny hosts=指定IP本网段指定IP

####文件末尾+:
```
[share]
    path=/share
	security=share
	public=no
	writable=yes
	browseable=yes
	writable
```
####启动方式：/etc/init.d/smbd start|stop|status


##selinux 在作怪
