Mac启用自带FTP服务

通过命令行来开启关闭，如下所示：

开启 FTP Server
sudo -s launchctl load -w /System/Library/LaunchDaemons/ftp.plist

关闭 FTP Server
sudo -s launchctl unload -w /System/Library/LaunchDaemons/ftp.plist

登录格式为 ftp://用户名@ip
然后输入你在Mac上的用户名和密码就可以了
