系统要求
CentOS 6+ / Debian 6+ / Ubuntu 14.04 +

脚本版本
Ver: 1.0.2

安装步骤
wget -N --no-check-certificate https://raw.githubusercontent.com/955124/bf/master/tinymapper.sh && chmod +x tinymapper.sh && bash tinymapper.sh
下载并运行脚本后，会显示操作菜单，输入1并回车就会开始安装。
-----------------------------------------------------------------------------------------------------------------------------
一键脚本安装V2Ray+WebSocket+TLS+Nginx救活被墙VPS


1.用root用户登入
1.1.进入谷歌云实例面板

1.2.切换到root角色
sudo -i
1
1.3.修改SSH配置文件/etc/ssh/sshd_config
vi /etc/ssh/sshd_config

修改PermitRootLogin和PasswordAuthentication为yes
PermitRootLogin yes
默认为no或without-passwd，需要开启root用户访问改为yes
PasswordAuthentication yes
默认为no，改为yes开启密码登陆
1.4.给root用户设置密码

passwd root
1.5.重启SSH服务使修改生效
/etc/init.d/ssh restart

bash <(curl -L -s https://raw.githubusercontent.com/955124/bf/master/v2ray.sh) | tee v2ray_ins.log

如果提示 curl: command not found ，那是因为你的小鸡没装 Curl
ubuntu/debian 系统安装 Curl 方法: apt-get update -y && apt-get install curl -y
centos 系统安装 Curl 方法: yum update -y && yum install curl -y
安装好 curl 之后就能安装脚本了

三、脚本启动方式

启动 V2ray：systemctl start v2ray

停止 V2ray：systemctl stop v2ray

启动 Nginx：systemctl start nginx

停止 Nginx：systemctl stop nginx

四、脚本相关目录

Web 目录：/home/wwwroot/levis

V2ray 服务端配置：/etc/v2ray/config.json

V2ray 客户端配置: 执行安装时所在目录下的 v2ray_info.txt

Nginx 目录： /etc/nginx

证书目录：/data/v2ray.key和/data/v2ray.crt
---------------------------------------------------------------------------------------------------------

一、BBR一键安装：

1、更换内核需要root权限，所以如果你是普通用户的话，需要root账号权限，如果你是root账号，那就忽略这个步骤：
sudo -i

2、BBR一键安装代码：
wget --no-check-certificate https://raw.githubusercontent.com/cx9208/Linux-NetSpeed/master/tcp.sh && chmod +x tcp.sh && ./tcp.sh

3、若报错运行以下代码，不报错跳过：
yum -y install wget
rm -f /var/run/yum.pid

3、重新打开脚本，查看是否运行成功：
./tcp.sh

二、ShadowsocksR一键安装：

简单的来说，如果你什么都不懂，那么你直接一路回车就可以了！

1、本脚本需要Linux root账户权限才能正常安装运行，所以如果不是 root账号，请先切换为root，如果是 root账号，那么请跳过！
sudo -i
输入上面代码回车后会提示你输入当前用户的密码，输入并回车后，没有报错就继续下面的步骤安装ShadowsocksR。

2、ShadowsocksR服务端一键安装：
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubiBackup/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh

运行脚本，输入对应的数字来执行相应的命令。
bash ssr.sh

三、客户端下载：
windows：https://github.com/shadowsocksrr/shadowsocksr-csharp/releases
android：https://github.com/shadowsocksrr/shadowsocksr-android/releases
mac os：https://github.com/qinyuhang/ShadowsocksX-NG-R/releases/

 yum update -y && yum install curl -y       (2).yum install wget

