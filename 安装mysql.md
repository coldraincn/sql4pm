1. *macOS环境*
## 下载地址
[macOS](https://dev.mysql.com/downloads/mysql/)  
如下图所示  
![下载图示](./images/mysqlmac1.png)  
点击“download”跳转到下页  
![下载图示2](./images/mysqlmac2.png)  
## 安装
1. 点击"mysql-8.0.15-macos10.14-x86_64.dmg"进行安装，双击pkg文件，一系列的继续输入密码后到"configuration",选择"use legacy password encryption"(选择此项密码方便设置记忆) ，然后点击"next"   
![密码选择](./images/mysqlmac3.png)  
2. 输入密码点击"finish"并完成 ,弹出电脑输入密码框，输入本电脑的密码 
![输入密码](./images/mysqlmac4.png)
3. 环境配置(终端操作在英文输入法下进行！！！)  
点击“启动台”-》“其他”-》“终端”  
![打开终端](./images/mysqlmac5.png)  
输入`sudo vim .bash_profile`，回车，输入密码后显示一个界面，  
![打开配置文件](./images/mysqlmac6.png)  
![配置文件](./images/mysqlmac7.png)  
点击键盘的`i`按键，界面下面有个"insert"，表示可以输入  
![insert](./images/mysqlmac8.png)  
然后输入`export PATH=${PATH}:/usr/local/mysql/bin`后点击键盘的`esc`按键，"insert"字消失  
![输入环境变量](./images/mysqlmac9.png)  
输入键盘的`:`,左下角显示如图  
![输入:](./images/mysqlmac10.png)  
然后输入`wq`回车进行保存，自动关闭返回终端界面    
![保存](./images/mysqlmac11.png)  
输入`source .bash_profile`或者重启终端，使环境生效  
![环境生效](./images/mysqlmac12.png)  
4. 测试  
输入`mysql -u root -p`回车，输入密码，显示`mysql>`字样，表示成功。 
![测试](./images/mysqlmac13.png)  
5. 如果无法启动mysql,点击“设置”-》最下面的“mysql”，如下图所示  
![mysql设置](./images/mysqlmac14.png)

2. *windows*环境
## 下载地址

[windows](https://dev.mysql.com/downloads/mysql/)  
如下图所示
![下载图示](./images/mysql1.png)
点击“download”按钮跳转到下页
![下载图示2](./images/mysql2.png)
点击“No thanks, just start my download.”开始下载
## 安装
1. 将下载的mysql-8.0.15-winx64移动到一个硬盘中，我的是d盘
![移动到安装盘](./images/mysql3.png)
2. 解压mysql-8.0.15-winx64
![解压](./images/mysql4.png)
3. 环境变量配置
进入bin文件夹
![bin](./images/mysql5.png)
鼠标放到红色箭头处，点下鼠标左键，复制路径
![复制路径](./images/mysql6.png)
右击“此电脑”选择“属性”  
![属性](./images/mysql7.png)  
点击“高级系统设置”  
![高级环境配置](./images/mysql8.png)  
点击“环境变量”  
![环境变量](./images/mysql9.png)  
选择“系统变量”中的”path“，点击“编辑”  
![path](./images/mysql10.png)  
点击“新建”并再下面的输入框中粘贴刚才复制的bin路径  
![复制路径](./images/mysql11.png)  
点击“确定”按钮，其他弹框一次点击“确定”按钮
![确定](./images/mysql12.png)  
4. 添加my.ini文件  
在mysql-8.0.15-winx64目录下新建“my.ini”文件  
![myini](./images/mysql19.png)  
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
![开打powershell](./images/mysql13.png)  
![选择管理员](./images/mysql14.png)  
首先填写刚在mysql解压到的硬盘，例如，我的是d盘，输入"D:"回车  
![选择硬盘](./images/mysql15.png)  
进入bin文件夹，输入"cd mysql-8.0.15-winx64\bin" 回车  
![进入bin](./images/mysql16.png)  
接着输入"mysqld --initialize --user=mysql --console"回车  
![initialize](./images/mysql20.png) 
*记住密码，我的是hf>wYypmY9/g，每个人不一样*  
然后输入"mysqld install"回车    
![install](./images/mysql17.png) 
6. 启动mysql，以后每次打开电脑使用mysql的时候，可以在powershell输入"net start mysql"  
![启动](./images/mysql21.png)
7. 进入数据库，输入"mysql -u root -p"然后输入刚才记住的密码  
![进入数据库](./images/mysql22.png)
8. 修改密码，刚才的密码太难用，进入数据库后，可以输入以下命令进行修改,以后输入mysql -u root -p后就可以输入自己的密码了
```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345678';
```  
![修改密码](./images/mysql23.png)  
9. 测试，输入 "shows databases;"  完成安装  
![测试](./images/mysql24.png)
10. 退出mysql，输入"exit;"  
![退出](./images/mysql25.png)