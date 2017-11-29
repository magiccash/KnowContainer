# ubuntu-17.04 安装 ssserver

### 安装 shadowsocks

apt-get install -y python-pip python-setuptools

pip install shadowsocks

vim /etc/shadowsocks.json

{
  "server":"45.77.166.204",
  "server_port":8388,
  "password":"magic@123",
  "timeout":600,
  "method":"aes-256-cfb",
  "fast_open":false,
  "workers": 3
}

ssserver -c /etc/shadowsocks.json -d start

ps -ef | grep 'ssserver'

ssserver -c /etc/shadowsocks.json -d stop


### 安装 google bbr

wget --no-check-certificate -qO 'BBR.sh' 'https://moeclub.org/attachment/LinuxShell/BBR.sh' && chmod a+x BBR.sh && bash BBR.sh -f v4.11.9

wget --no-check-certificate -qO 'BBR_POWERED.sh' 'https://moeclub.org/attachment/LinuxShell/BBR_POWERED.sh' && chmod a+x BBR_POWERED.sh && bash BBR_POWERED.sh -f v4.11.9
