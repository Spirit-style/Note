#vscode java运行环境配置
1. 下载maven 
>https://maven.apache.org/download.cgi?Preferred=http%3A%2F%2Fmirrors.hust.edu.cn%2Fapache%2F
2. 解压
>sudo tar -zxvf apache-maven-3.6.0-bin.tar.gz
3. 移动 
>sudo mv apache-maven-3.6.0 /java/apache-maven-3.6.0
4. 配置环境变量
>export M2_HOME=/java/apache-maven-3.6.0
>export PATH=$PATH:${M2_HOME}/bin
5. 重启配置文件
>source ~/.bashrc
6. 验证是否安装成功
>mvn -v
7. 下载vscode Java插件
    :bulb:Language Support for Java(TM) by Red Hat：通过 Eclipse ™ JDT Language Server 提供 Java 语言支持
    :bulb:Debugger for Java：基于 Java Debug Server 的轻量级调试工具。
    :bulb:Java Test Runner：执行和调试 Java 测试用例。
    :bulb:Maven for Java：Maven 插件。
8.
