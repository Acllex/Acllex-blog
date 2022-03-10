## 常用组件及软件包

```shell
##Debian安装命令###
apt-get update && apt-get install unzip zip wget curl  mc  nano sudo ufw socat ntp ntpdate gcc git vim socat make build-essential cmake libboost-system-dev libboost-program-options-dev libssl-dev default-libmysqlclient-dev netcat dnsutils -y
##CentOS安装命令###
yum update -y && yum install unzip zip wget curl  mc  nano sudo ufw socat ntp ntpdate gcc git vim socat make build-essential cmake libboost-system-dev libboost-program-options-dev libssl-dev default-libmysqlclient-dev netcat net-tools-y
解析是否生效检测网站：https://www.whatsmydns.net/
```

## 安装 acme

```shell
##安装acme##
curl https://get.acme.sh | sh
source ~/.bashrc

##建个文件夹存放证书和密钥##
rm -rf /home/tls && mkdir -p /home/tls
```

```shell
##standalone 模式（申请单个域名证书)##
确保 80 端口未被占用：netstat -nlpt 关闭进程 kill pid 停止服务 systemctl stop 服务名
添加解析 A 记录域名到 VPS 的 IP 地址
申请证书
acme.sh --issue -d or.acllex.ga --standalone
安装证书
acme.sh --install-cert -d or.acllex.ga --fullchain-file /home/tls/or.acllex.ga.crt --key-file /home/tls/or.acllex.ga.key
```
