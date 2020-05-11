##  配置CentoS7虚拟机
1. 将网络适配器设置成网桥模式（通过路由器连接）；
2. dhclient 找到一个没有使用的IP， su root模式；
3. ifconfig查询ip和网卡名称；
4. 配置静态ip  /etc/sysconfig/network-scripts文件夹下的ifcfg-ens33文件

```
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=ens33
UUID=1b3cfdab-f123-43bc-92c9-573cddbe6d39
DEVICE=ens33
ONBOOT=yes
IPADDR=192.168.1.109
NETMASK=255.255.255.0
GATEWAY=192.168.1.1
DNS1=192.168.1.1
```
5.重启网卡  systemctl restart network.service
6.和宿主机互ping IP

## Ubuntu虚拟机网络配置
1. 更改网络配置，桥式连接；
2. ifconfig查询ip地址，记录网卡名称和ip地址
3. 将动态ip改为静态ip。修改网卡配置文件sudo  vim /etc/network/interfaces
4. interfaces文件修改 
auto 网卡名称
iface ens33 inet static
address ip
netmask 255.255.255.0
gateway 根据宿主机的网关
5. 修改DNS 和网关一致  /etc/resolv.conf
6. 重启网络服务 $ sudo /etc/init.d/networking restart（注意要重启虚拟机）
7. 宿主机和虚拟机互ping ip地址，完成网络配置。
8. 下载服务器端openssh-server

### 修改Ubuntu apt下载源
1. sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
2. sudo vim /etc/apt/sources.list
```
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
```
3. apt-get update