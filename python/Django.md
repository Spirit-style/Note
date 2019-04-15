#命令
>django-admin start
Available subcommands:

[django]
    check   验证项目完整性
    compilemessages
    createcachetable
    dbshell
    diffsettings
    dumpdata   将数据库数据导出到文件
    flush
    inspectdb
    loaddata    将文件数据导入到数据库
    makemessages 
    makemigrations 创建模型变更的迁移文件
    migrate        执行上一个命令创建的迁移文件
    runserver      本地简易运行django项目
    sendtestemail
    shell 
    showmigrations
    sqlflush
    sqlmigrate
    sqlsequencereset
    squashmigrations
    startapp        创建应用 python manage.py startapp one
    startproject    创建项目
    test             djingo的用例测试
    testserver


urls.py 路由配置文件
setting.py 项目配置文件
manage.py 项目管理文件
wsgi.py  

视图：
    实现产生内容功能
    1. 新建一个应用，在视图文件中添加函数
    2. 配置应用路由
    3. 配置项目路由
    4. 修改项目配置文件installed_apps

模型层：
    作用：位于视图和数据库之间的组件，屏蔽不同数据库之间的差异
    配置：
路由：