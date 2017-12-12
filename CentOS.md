# 安装nginx
yum -y install nginx
# 安装mysql 
wget https://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm
rpm -ivh mysql57-community-release-el7-11.noarch.rpm
yum -y install mysql-community-server

service mysqld start
在5.7版本的MySQL启动时，因为数据目录是空的，所以会有以下操作：

服务器初始化
在数据目录生成一个SSL证书和key文件
validate_password插件安装并启用
创建一个超级管理帐号'root'@'localhost'。管理的密码会保存在错误日志文件中，可以通过以下命令查看：
$ sudo grep 'temporary password' /var/log/mysqld.log
可以通过以下命令并使用自动生成的临时密码登录，然后修改为一个自定义密码：

$ mysql -u root -p 
密码修改：

$ ALTER USER 'root'@'localhost' IDENTIFIED BY 'newPassword';
注意：MySQL的validate_password插件是默认安装的。这要求MySQL密码至少包含一个大写字母、一个小写字母、一个数字和一个特殊字符，并且总密码长度至少为8个字符。

# 安装java
rpm -ivh jdk-8u101-linux-x64.rpm
