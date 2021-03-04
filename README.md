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

* Django连接MySQL的时候，会遇到需要安装cryptography，安装cryptography时可以参考如下地址：https://www.cnblogs.com/huangyumei/p/6097200.html
安装cryptography过程中，同事需要安装openssl，openssl通常需要编译，编译方式很复杂，因此建议直接到第三方下载已经编译好的exe文件进行安装，https://blog.csdn.net/qq_39081974/article/details/81059022
* 如果openssl,rust的问题不好解决的话，或者尝试将版本安装，会出错VC++ 14.0的问题；
* Microsoft Visual C++ 14.0 is required的解决方法：https://blog.csdn.net/qq_38161040/article/details/87929616
* 最终解决这个问题，pip install cryptography -i http://pypi.douban.com/simple --trusted-host pypi.douban.com；解决了之前pip install xxx在线安装出现There was a problem confirming the ssl certificate的问题。直接安装就不存在rust的问题；
*
