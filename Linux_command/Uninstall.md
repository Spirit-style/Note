# 卸载过期内核
目的：为解决/boot内存不足  
```shell
$uname -a 查看正在使用的内核
$dpkg --get-selections|grep linux-image  查看所有内核的状态
$sudo apt-get remove linux-image-4.15.0-29-generic 卸载相印版本的内核
$df -h 查看内存状态
```