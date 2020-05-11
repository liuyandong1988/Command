# ubuntu装机
## 1. 更改apt-get源
#首先备份源列表
sudo cp /etc/apt/sources.list /etc/apt/sources.list_backup
sudo vim /etc/apt/sources.list
#https://opsx.alibaba.com/mirror
deb https://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse 
deb https://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse 
deb https://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse 
deb https://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse 
deb https://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse 

#仿照清华镜像源，注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
#deb-src https://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse 
#deb-src https://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse 
#deb-src https://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse 
#deb-src https://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse 
#deb-src https://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse

## 2.更新显卡
software updater --- setting -- addition drivers

## 3.安装搜狗输入法
下载 package https://pinyin.sogou.com/linux/
安装下载文件，配置fcitx， **安装fcitx后需要重启电脑**

## 4. 安装VPN （购买surfshark-VPN）或者 github下载lantern
* sudo apt-get install openvpn unzip
* 修改DNS服务器
sudo su
chartt -i /etc/resolv.conf
vim /etc/resolve.conf
nameserver 162.252.172.57
nameserver 149.154.159.92
chartt +i /etc/resolv.conf
reboot now
* 找到surfshark 提供的ovpn文件
* sudo openvpn 不同的服务器.ovpn
* SURFSHARK   
id:           2f4qdRSSqqQ656UTW3ubJa6n 
code:     xQ5vWBbA8JTXezK62VyS5ybK

## 5. 安装配置git  githubDesktop
sudo apt-git install git
github desktop for ubuntu

```
wget https://github.com/shiftkey/desktop/releases/download/release-2.0.4-linux1/GitHubDesktop-linux-2.0.4-linux1.snap
snap remove github-desktop
snap install GitHubDesktop-linux-2.0.4-linux1.snap --classic --dangerous
```

## 6.zsh 终端配置
[zsh](https://www.jianshu.com/p/4fde9ae77922) 查询相关安装与配置

1. zsh: apt-get install zsh 

2. oh-my-zsh安装 链接外网不好用，git clone 下载源码到 .oh-my-zsh文件夹下；

3. ```shell
   cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc 配置文件复制
   ```

4. source ~/.zshrc

5. 插件安装 autojump，补全incr.zsh
   下载并安装 
   source /home/dong/.oh-my-zsh/plugins/incr/incr-0.2.zsh

   

## 7. 安装google chrome 并同步
官网下载 .deb 
sudo dpkg -i ×××.deb安装 
并安装相关配置


## 8.安装anaconda配置pycharm IDE
参见bilibili 北大课程tensorflow2
https://www.bilibili.com/video/BV1B7411L7Qt?from=search&seid=15241303904476568959


## 9. 安装VScode 配置C++环境
知乎 https://www.zhihu.com/search?type=content&q=vscode%20C%2B%2B

## 10. 虚拟机配置多节点linux环境
bilibili https://www.bilibili.com/video/BV1bA411b7vs?t=692


## ssh远程控制配置
知乎 https://zhuanlan.zhihu.com/p/108972475




* 护眼模式     redshift-gtk -l 39.92:116.46 -t 5000:4000 
* pip国内源  pip install -i https://pypi.tuna.tsinghua.edu.cn/simple 
* 登录远程服务器  ssh username@ip
* mp4 转 gif 

ffmpeg -ss 00:00:00 -i guess.mp4 -to 80 -r 100 -vf scale=200:-1 guess.gif
 -ss 表示起始点
 -i 后面跟要操作的那个视频文件
 -to 表示文件的终止点
 -r 帧速率，可以增大这个值输出更画质更优的 GIF 文件
 -vf 图形筛选器，GIF 的缩放大小

ffmpeg -i guess.mp4 guess.gif





SURFSHARK

2f4qdRSSqqQ656UTW3ubJa6n

xQ5vWBbA8JTXezK62VyS5ybK

DNS服务器

nameserver 219.147.198.230
nameserver 162.252.172.57
nameserver 149.154.159.92