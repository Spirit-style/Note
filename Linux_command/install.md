#软件安装步骤
```shell
$gcc -v  查看版本号
$sudo apt-get install gcc
碰到问题：
   更换介质：请把标有
   “Ubuntu 18.04.1 LTS _Bionic Beaver_ - Release amd64 (20180725)”的盘片插入驱动器“/cdrom/”再按「回车」键
解决问题：
   root权限修改/etc/apt/sources.list文件，注释掉deb cdrom:开头的行

```
#安装java jdk-11.0.1  
jdk-11.0.1中没有jre文件。  
1. 下载jdk  
``http://www.oracle.com/technetwork/java/javase/downloads/index.html``  
2. 解压  
``$ sudo tar -zxvf jdk-11.0.1_linux-x64_bin.tar.gz``  
3. 移动  
``$ sudo mv jdk-11.0.1 /usr/lib/java``  
4. 配置环境变量  
使用全局设置方法，它是所有用户的共用的环境变量  
```shell
   export JAVA_HOME= #这里填写你安装的路径
   export CLASSPATH =.: ${JAVA_HOME}/lib
   export PATH = ${JAVA_HOME}/bin:$PATH

   export JAVA_HOME= /java
   export CLASSPATH =.: ${JAVA_HOME}/lib
   export PATH = ${JAVA_HOME}/bin:$PATH

   遇到错误：
      lz@Zeng-Ubuntu:/$source ~/.bashrc
      bash: export: `/java': 不是有效的标识符
      bash: export: `=.:/lib': 不是有效的标识符
      bash: export: `=': 不是有效的标识符
      bash: export: `/bin:PATH': 不是有效的标识符
   
   错误原因：
      export JAVA_HOME=/java 的 “=”左右两边不能有空格。
```
5. 重启配置文件
   ``source ～/.bashrc``
6. 检查是否安装成功
   ``java -version``
7. 错误信息
解决方法
环境变量有问题，错误或者不恰当地修改了环境变量，将导致Linux自带的脚本命令不可用。
vi /etc/profile
在末尾加上
``export PATH="$PATH:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games"``

8. 通常设置环境变量有三种方法：
   临时设置
   当前用户的全局设置  
      ~/.bashrc
   所有用户的全局设置  
      /etc/profile  

      
      