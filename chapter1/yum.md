# 1.1 配置时间

在 CentOS 中配置时间首先你需要修改时区。

## 显示时区

`[root@ossez ~]# date +%z`

`-0400`

这里显示的时间是美国东部时间，-0400 的时区

系统中的时间文件保存在：/usr/share/zoneinfo 路径下

![](/assets/2017-03-30_10-27-25.jpg)

## 修改时区

假设你希望将服务器的时区修改为美国东部时间

可以运行下面的命令：

```
[gaarai@server ~]$ sudo mv /etc/localtime /etc/localtime.bak
[gaarai@server ~]$ sudo ln -s /usr/share/zoneinfo/America/New_York /etc/localtime
```





