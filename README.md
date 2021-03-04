# MySQL_Install

MySQL安装中所遇到的问题，记录如下。
* 主要的安装指导：https://www.runoob.com/mysql/mysql-install.html
* windows用户，已管理员身份启动cmd
* mysqld --initialize --console进行初始化的时候，如果出现vcruntime140_1.dll缺失，就死VC2015没有安装，直接下载安装VC2015即可，或者往上搜索vcruntime140_1.dll并安装（https://www.jb51.net/dll/vcruntime140_1.dll.html）
* mysqld --initialize --console成功，如果提示文件存在什么的，可以直接删掉install_dir\data目录
* 关于提示UTF8的字体警告，是mysql不支持UTF8,mysql为了解决该问题，可以参考https://www.jb51.net/article/151274.htm
* 在初始化之前，需要保证磁盘空间较大
* 登陆时候，如果出现ERROR 2003 (HY000)的问题，是没有启动MySQL服务；需要net start mysql或者手动打开Windows服务，开启mysql服务，然后在登陆；若反复出现开启了mysql服务，但是仍然登陆不上的话，可以删掉之前install_dir\data目录,重新初始化mysql;
* 登陆上mysql之后，需要更改密码：set password='密码'
