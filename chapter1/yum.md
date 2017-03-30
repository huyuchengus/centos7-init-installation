# 1.1 配置时间

在 CentOS 中配置时间首先你需要修改时区。

## 显示时区

`[root@ossez ~]# date +%z`

`-0400`

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

## 安装 NTP

安装 NTP 服务

```
yum install ntp
```

将 NTP 的防火墙打开，NTP 服务使用的是 UDP 123 端口。

```
# firewall-cmd --add-service=ntp --permanent
# firewall-cmd --reload
```

![](/assets/2017-03-30_10-38-18.jpg)

启动 NTP 服务

```
# systemctl start ntpd
# systemctl enable ntpd
# systemctl status ntpd
```

![](/assets/2017-03-30_10-40-03.jpg)

更多有关 NTP 的命令和使用，请参考下面的链接。一般来说服务器配置到这里就可以了，因为你的 ntp 服务会根据你配置的时间状态对你的服务器时间进行同步。

---

* [http://www.ossez.com/thread-31578-1-1.html](http://www.ossez.com/thread-31578-1-1.html "CentOS7 配置时间")
* [http://www.ossez.com/thread-31579-1-1.html](http://www.ossez.com/thread-31579-1-1.html "CentOS7 安装 NTP")



