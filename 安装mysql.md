# 1. *macOS环境*
## 下载地址
[macOS](https://dev.mysql.com/downloads/mysql/)  
如下图所示  
![下载图示](http://img.coldraincn.com/sql/mysqlmac1.png)  
点击“download”跳转到下页  
![下载图示2](http://img.coldraincn.com/sql/mysqlmac2.png)  
## 安装
1. 点击"mysql-8.0.15-macos10.14-x86_64.dmg"进行安装，双击pkg文件，一系列的继续输入密码后到"configuration",选择"use legacy password encryption"(选择此项密码方便设置记忆) ，然后点击"next"   
![密码选择](http://img.coldraincn.com/sql/mysqlmac3.png)  
2. 输入密码点击"finish"并完成 ,弹出电脑输入密码框，输入本电脑的密码 
![输入密码](http://img.coldraincn.com/sql/mysqlmac4.png)
3. 环境配置(终端操作在英文输入法下进行！！！)  
点击“启动台”-》“其他”-》“终端”  
![打开终端](http://img.coldraincn.com/sql/mysqlmac5.png)  
输入`sudo vim .bash_profile`，回车，输入密码后显示一个界面，  
![打开配置文件](http://img.coldraincn.com/sql/mysqlmac6.png)  
![配置文件](http://img.coldraincn.com/sql/mysqlmac7.png)  
点击键盘的`i`按键，界面下面有个"insert"，表示可以输入  
![insert](http://img.coldraincn.com/sql/mysqlmac8.png)  
然后输入`export PATH=${PATH}:/usr/local/mysql/bin`后点击键盘的`esc`按键，"insert"字消失  
![输入环境变量](http://img.coldraincn.com/sql/mysqlmac9.png)  
输入键盘的`:`,左下角显示如图  
![输入:](http://img.coldraincn.com/sql/mysqlmac10.png)  
然后输入`wq`回车进行保存，自动关闭返回终端界面    
![保存](http://img.coldraincn.com/sql/mysqlmac11.png)  
输入`source .bash_profile`或者重启终端，使环境生效  
![环境生效](http://img.coldraincn.com/sql/mysqlmac12.png)  
4. 测试  
输入`mysql -u root -p`回车，输入密码，显示`mysql>`字样，表示成功。 
![测试](http://img.coldraincn.com/sql/mysqlmac13.png)  
5. 如果无法启动mysql,点击“设置”-》最下面的“mysql”，如下图所示  
![mysql设置](http://img.coldraincn.com/sql/mysqlmac14.png)  

6. 卸载 
依次输入一下命令  

    ```
    sudo rm /usr/local/mysql
    sudo rm -rf /usr/local/mysql*
    sudo rm -rf /Library/StartupItems/MySQLCOM
    sudo rm -rf /Library/PreferencePanes/My*
    edit /etc/hostconfig and remove the line MYSQLCOM=-YES-
    rm -rf ~/Library/PreferencePanes/My*
    sudo rm -rf /Library/Receipts/mysql*
    sudo rm -rf /Library/Receipts/MySQL*
    sudo rm -rf /private/var/db/receipts/*mysql*
    sudo rm -rf .bash_profile
    sudo rm -rf /usr/local/etc/my.cnf*
    ```  

    ```
    192:Desktop apple$ sudo rm /usr/local/mysql
    Password:
    192:Desktop apple$ sudo rm -rf /usr/local/mysql*
    192:Desktop apple$ sudo rm -rf /Library/StartupItems/MySQLCOM
    192:Desktop apple$ sudo rm -rf /Library/PreferencePanes/My*
    192:Desktop apple$ edit /etc/hostconfig and remove the line MYSQLCOM=-YES-
    -bash: edit: command not found
    192:Desktop apple$ rm -rf ~/Library/PreferencePanes/My*
    192:Desktop apple$ sudo rm -rf /Library/Receipts/mysql*
    192:Desktop apple$ sudo rm -rf /Library/Receipts/MySQL*
    192:Desktop apple$ sudo rm -rf /private/var/db/receipts/*mysql*
    192:Desktop apple$
    ```  
    再次查看设置里，发现mysql的小鲸鱼（海豚)消失，表示已经删除了^_^  

    ![删除](http://img.coldraincn.com/sql/mysqlmac19.png)

# 2. *windows*环境
## 下载地址

[windows](https://dev.mysql.com/downloads/mysql/)  
如下图所示
![下载图示](http://img.coldraincn.com/sql/mysql1.png)
点击“download”按钮跳转到下页
![下载图示2](http://img.coldraincn.com/sql/mysql2.png)
点击“No thanks, just start my download.”开始下载
## 安装
1. 将下载的mysql-8.0.15-winx64移动到一个硬盘中，我的是d盘
![移动到安装盘](http://img.coldraincn.com/sql/mysql3.png)
2. 解压mysql-8.0.15-winx64
![解压](http://img.coldraincn.com/sql/mysql4.png)
3. 环境变量配置
进入bin文件夹
![bin](http://img.coldraincn.com/sql/mysql5.png)
鼠标放到红色箭头处，点下鼠标左键，复制路径
![复制路径](http://img.coldraincn.com/sql/mysql6.png)
右击“此电脑”选择“属性”  
![属性](http://img.coldraincn.com/sql/mysql7.png)  
点击“高级系统设置”  
![高级环境配置](http://img.coldraincn.com/sql/mysql8.png)  
点击“环境变量”  
![环境变量](http://img.coldraincn.com/sql/mysql9.png)  
选择“系统变量”中的”path“，点击“编辑”  
![path](http://img.coldraincn.com/sql/mysql10.png)  
点击“新建”并再下面的输入框中粘贴刚才复制的bin路径  
![复制路径](http://img.coldraincn.com/sql/mysql11.png)  
点击“确定”按钮，其他弹框一次点击“确定”按钮
![确定](http://img.coldraincn.com/sql/mysql12.png)  
4. 添加my.ini文件  
在mysql-8.0.15-winx64目录下新建“my.ini”文件  
    ![myini](http://img.coldraincn.com/sql/mysql19.png)  
    打开my.ini输入以下文字(basedir和datadir填入自己的mysql解压文件夹）：  
    ```
    [mysqld]
    # 设置3306端口
    port=3306
    # 设置mysql的安装目录
    basedir=D:\\mysql-8.0.15-winx64
    # 设置mysql数据库的数据的存放目录
    datadir=D:\\mysql-8.0.15-winx64\\data
    # 允许最大连接数
    max_connections=200
    # 允许连接失败的次数。这是为了防止有人从该主机试图攻击数据库系统
    max_connect_errors=10
    # 服务端使用的字符集默认为UTF8
    character-set-server=utf8
    # 创建新表时将使用的默认存储引擎
    default-storage-engine=INNODB
    [mysql]
    # 设置mysql客户端默认字符集
    default-character-set=utf8
    [client]
    # 设置mysql客户端连接服务端时默认使用的端口
    port=3306
    default-character-set=utf8
    ```


5. 执行安装初始化
鼠标右键点击左下角的”窗口“选择 “windows powershell 管理员” 
![开打powershell](http://img.coldraincn.com/sql/mysql13.png)  
![选择管理员](http://img.coldraincn.com/sql/mysql14.png)  
首先填写刚在mysql解压到的硬盘，例如，我的是d盘，输入"D:"回车  
![选择硬盘](http://img.coldraincn.com/sql/mysql15.png)  
进入bin文件夹，输入"cd mysql-8.0.15-winx64\bin" 回车  
![进入bin](http://img.coldraincn.com/sql/mysql16.png)  
接着输入"mysqld --initialize --user=mysql --console"回车  
![initialize](http://img.coldraincn.com/sql/mysql20.png) 
*记住密码，我的是hf>wYypmY9/g，每个人不一样*  
然后输入"mysqld install"回车    
![install](http://img.coldraincn.com/sql/mysql17.png) 
6. 启动mysql，以后每次打开电脑使用mysql的时候，可以在powershell输入"net start mysql"  
![启动](http://img.coldraincn.com/sql/mysql21.png)
7. 进入数据库，输入"mysql -u root -p"然后输入刚才记住的密码  
![进入数据库](http://img.coldraincn.com/sql/mysql22.png)  
8. 修改密码，刚才的密码太难用，进入数据库后，可以输入以下命令进行修改,以后输入mysql -u root -p后就可以输入自己的密码了  

    ```sql
    ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345678';
    ```   

    ![修改密码](http://img.coldraincn.com/sql/mysql23.png)   

9. 测试，输入 "shows databases;"  完成安装   

    ![测试](http://img.coldraincn.com/sql/mysql24.png)  

10. 退出mysql，输入"exit;"   

    ![退出](http://img.coldraincn.com/sql/mysql25.png)  


# 3. macOS使用homebrew安装（较为简单）  
## 安装homebrew  
> Homebrew是一款Mac OS平台下的软件包管理工具，拥有安装、卸载、更新、查看、搜索等很多实用的功能。简单的一条指令，就可以实现包管理，而不用你关心各种依赖和文件路径的情况，十分方便快捷。  

1. 打开链接[homebrew](https://brew.sh/)  
2. 打开终端，将下面图中箭头指向的语句`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`复制到终端，回车进行安装  
    ![安装brew](http://img.coldraincn.com/sql/brew1.png)   
    如果终端出现`Press RETURN to continue or any other key to abort`光标会停止,点击回车键继续  
    ![继续安装](http://img.coldraincn.com/sql/brew2.png)
3. 更新下homebrew，如果homebrew已经安装，最好更新下，以便我们能获取到最新的软件，在终端使用命令`brew updata`,  

    ```
    192:~ apple$ brew update
    Already up-to-date.
    192:~ apple$ 
    ``` 

4. 安装mysql  
在终端输入命令`brew install mysql`  

    ![安装mysql](http://img.coldraincn.com/sql/brew3.png)  

5. 启动服务
我们再次打开设置，里面没有mysql小鲸鱼（海豚）图标，要想启动服务，我们使用终端，在终端中输入`brew services start mysql`或者
`mysql.server start`,建议第一种，建议每次开机使用mysql的时候都输入`brew services start mysql`确保服务已经启动 （停止服务使用命令`brew services stop mysql`或者`mysql.server stop`,重启服务使用`brew services restart mysql`或者`mysql.server restar`,注意命令是对应的，使用一个命令(例如bew services start mysql)开启，那么必须使用相应的命令关闭或重启(brew services stop mysql)  

    ```
    192:~ apple$ brew services start mysql
    ==> Tapping homebrew/services
    Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-services'...
    remote: Enumerating objects: 17, done.
    remote: Counting objects: 100% (17/17), done.
    remote: Compressing objects: 100% (14/14), done.
    remote: Total 17 (delta 0), reused 12 (delta 0), pack-reused 0
    Unpacking objects: 100% (17/17), done.
    Tapped 1 command (50 files, 62.7KB).
    ==> Successfully started `mysql` (label: homebrew.mxcl.mysql)
    192:~ apple$ 
    ```  

6. 登录，使用homebrew安装的mysql没有密码，使用`mysql -u root -p`回车后在输入密码那里不需要输入密码，再次回车登陆  
7. 修改密码，登陆mysql后使用命令 `alter user 'root'@'localhost' identified  by '新密码';`，或者输入`mysql_secure_installation`,按照提示设置  

    ```
    mysql> alter user 'root'@'localhost' identified  by '12345678';
    Query OK, 0 rows affected (0.00 sec)

    mysql> 
    ```  

8. 退出重新登陆  在终端输入`exit;`，退出mysql，重新输入`mysql -u root -p`回车，输入我们刚才修改的命令，登陆mysql进行使用。 
9. 修改配置文件，使用brew安装mysql，会自动为我们加入my.cnf配置文件，路径在`/usr/local/etc/my.cnf`, 我们使用命令`sudo vim /usr/local/etc/my.cnf`,重新打开终端，输入上述命令,如果要求输入密码则输入密码，回车   

    ![vim1](http://img.coldraincn.com/sql/vim1.png)  

    输入密码后，显示如图  

    ![vim2](http://img.coldraincn.com/sql/vim2.png)  
    点击键盘按钮`i`,界面下面会有insert字样，表示可以输入修改 ，然后使用键盘的上下左右键，将光标移动到末尾。  

    ![vim3](http://img.coldraincn.com/sql/vim3.png) 

    然后回车进入下一行，输入`secure-file-priv = ""`，参考[导入导出以及可视化](导入导出以及可视化.md)->导出数据库->4导出查询的数据  

    ![vim4](http://img.coldraincn.com/sql/vim4.png)  

    接着点击键盘的`esc`按键，退出输入模式，左下角的insert字样消失  

    ![vim5](http://img.coldraincn.com/sql/vim5.png)  

    insert字样消失后，点击键盘的`:`冒号，左下角会有个冒号的标示，光标紧随在后    

    ![vim6](http://img.coldraincn.com/sql/vim6.png)  

    然后输入`wq`,回车,进行保存以及关闭  

    ![vim7](http://img.coldraincn.com/sql/vim7.png)   

    最后在终端输入`brew services restart mysql`重启mysql，然后我们就可以使用[导入导出以及可视化](导入导出以及可视化.md)->导出数据库->4导出查询的数据了,而且可以随意导出数据到任何文件夹（以前是只能tmp),登陆mysql,use 一个数据库，使用`select * from test into outfile '/Users/apple/Desktop/fdfd.xls';`, 导出到桌面^_^

10. 删除mysql，在终端中输入`brew uninstall mysql`,然后输入`brew cleanup`



