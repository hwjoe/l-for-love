# MySQL 8重置密码的办法( 老方法不灵了 ) #

MySQL的密码是存放在user表里面的，修改密码其实就是修改表中记录。

重置的思路是是想办法不用密码进入系统，然后用数据库命令修改表user中的密码记录。

MySQL5系统在网上建议的方法是以–skip-grant-tables参数启动mysql服务，该参数指示在启动时不加载授权表，因此启动成功后root用户可以空密码登陆

    mysqld –skip-grant-tables

登陆之后可以用

    UPDATE user SET authentication_string=” WHERE user=’root’;

这类命令设置密码或者将密码置空。

但是，实测mysqld –skip-grant-tables这样的命令行，在mysql8中无法成功启动，而且测试了该参数放在ini文件里面也同样无法启动

MySQL8系统密码重置的两个思路

两条思路，或者用–init-file参数在服务启动时加载并运行修改密码的命令文件，该命令一旦执行，服务启动后密码即已经清除或者重置，启动服务后即可以空密码或指定密码登入。

或者继续研究–skip-grant-tables命令行参数下服务不能启动的原因，解决问题，然后启动服务后以空密码登入，手工输入命令，执行清除或者重置mysql.user表中的密码记录字段。

推荐使用前者。

具体操作流程如下：

方法一:利用–init-file参数解决

该参数指定服务启动时先执行一个包含sql命令文件，因此，只需要将重置密码的命令写在该文件中，以此参数指定启动时执行该命令，启动完成即可重置系统密码了。

第一步，关掉系统服务

    net stop mysql

第二步，创建一个文本文件，内含一条密码修改命令

    ALTER USER ‘root’@’localhost’ IDENTIFIED BY ”;

第三步：命令行方式启动服务器，指定启动时执行上述的密码修改命令文件

    mysqld –init-file=d:mysqlc.txt –console

方法二，想办法让–skip-grant-tables参数用起来

同方法一，先关掉系统服务

实测，在mysql8系统下，用mysqld –console –skip-grant-tables –shared-memory可以无密码启动服务

服务启动后，以空密码登入系统

    mysql.exe -u root

然后执行sql命令将root用户密码设置为空

    UPDATE mysql.user SET authentication_string=” WHERE user=’root’ and host=’localhost’; 

 MySQL8的一些特性导致老方法重置不大管用了，建议使用–init-file参数解决，实测安全可靠。

数据库管理密码丢失是很头疼的事情，如果不能顺利找回，麻烦很大。网上搜索的解决方法多数已经落伍，建议收藏关注本文，以备不时之需。

链接：http://codebay.cn/post/9447.html
