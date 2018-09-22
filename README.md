Linux基础
=====
## Centos6

/dev/sda,b,c,...z,aa,ab,ac,az,ba,

分区：MBR，GPT

主：一个硬盘最多四个分区，只有一个是活动，1 - 4

拓展：最多一个，划分更小的分区，拓展+主分区<=4  1 - 4

逻辑分区：5，6

## 分区规划：
> /50&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;G   
> /boot&ensp;&ensp;&ensp;&ensp;1G   
> /data&ensp;&ensp;&ensp;&ensp;30G   
> swap  交换分区 2G  Centos7.5  centos6.10 1G

ctrl+enter 全屏  
ctrl+alt 鼠标移动  
ifconifig配置网络设备  


## 用户登录
* root用户  
&ensp;&ensp;&ensp;&ensp;一个特殊的管理账户  
&ensp;&ensp;&ensp;&ensp;也被称为超级用户   
&ensp;&ensp;&ensp;&ensp;root已接近完整的系统控制   
&ensp;&ensp;&ensp;&ensp;对系统损害几乎有无限可能的能力   
&ensp;&ensp;&ensp;&ensp;除非必要，不要登陆为root   
* 普通（非特权）用户  
&ensp;&ensp;&ensp;&ensp;权限有限   
&ensp;&ensp;&ensp;&ensp;造成损害的能力比较有限   

## 终端
* 设备终端terminal  
&ensp;&ensp;&ensp;&ensp;键盘鼠标显示器  
* 物理终端（/dev/console）  
&ensp;&ensp;&ensp;&ensp;控制台console  
* 虚拟终端（tty：teletypewriters, &ensp;&ensp;/decv/tty#&ensp;&ensp;#为[1-6]）   
&ensp;&ensp;&ensp;&ensp;CentOs&ensp;6Ctrl+Alt+F7    
&ensp;&ensp;&ensp;&ensp;CentOs&ensp;7:在哪个终端启动，即位于哪个虚拟终端   
* 串行终端（/dec/ttyS#）   
&ensp;&ensp;&ensp;&ensp;ttys   
* 伪终端（pty：pseudo,&ensp;&ensp;dev/pts/#）   
&ensp;&ensp;&ensp;&ensp;pty,SSH远程连接  
* 查看当前的终端设备：   
&ensp;&ensp;&ensp;&ensp;tty   

## 交互式接口
* 交互式接口：启动终端后，在终端设备附加一个交互式应用设备   
   
* GUI：Graphic&ensp;User&ensp;Interface  
&ensp;&ensp;&ensp;&ensp;X&ensp;protocol,window&ensp;manager,desktop   
&ensp;&ensp;&ensp;&ensp;&ensp;Desktop:
&ensp;&ensp;&ensp;&ensp;&ensp;GNOME(C,图形库gtk)   
&ensp;&ensp;&ensp;&ensp;&ensp;KDE&ensp;&ensp;(C++,图形库gtk)   
&ensp;&ensp;&ensp;&ensp;&ensp;CFCE(轻量级桌面)
 * CLI :Command Line Interface  
       Shell程序：sh(bourn史蒂夫·伯恩)csh&ensp;&ensp;tash&ensp;&ensp;ksh(korn)&ensp;&ensp;bash(bourn&ensp;&ensp;again&ensp;&ensp;shell )GPL&ensp;&ensp;zsh

## 什么是shell
- Shell是Linux系统的用户界面，提供了用户与内核进行交互操作的一种接口。它接收用户输入的命令并把它送入内核去执行  
- Shell也被称为LINUX的命令解释器（command&ensp;&ensp;interpreter）  
- shell是一种高级编程设计语言  
![googel](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1537617925766&di=9ab9cf316639c0e447d025cd8d1ddade&imgtype=0&src=http%3A%2F%2Fimage001.server110.com%2F20170319%2Ff01ad32ae79f1ed7c18a54d06b7ee0d6.png)   
## bash shell
- GNU Bourne-Again Shell(bash)是GUN计划中重要的工具软件之一，目前也是Linux标准的shell,与sh兼容
- CentOs默认使用
- 显示当前使用的shell  
&ensp;&ensp;echo${SHELL}
- 显示当前系统使用的所有shell  
&ensp;&ensp;cat/etc/shells
## 命令提示符
- 命令提示符：prompt  
[root@localhost~]#  
&ensp;&ensp;&ensp;&ensp;#管理员  
&ensp;&ensp;&ensp;&ensp;$普通用户  
- 显示提示符格式
&ensp;&ensp; [root@localhost~]#echo&ensp;&ensp;$PS1
- 修改提示符格式  
&ensp;&ensp;PS1=“\[\e[1;5;41;33m\][\u@\h\W]\\$\[\e[0m\]"   
&ensp;&ensp;\e\033&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;\u当前用户     
&ensp;&ensp;\h 主机名简称&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;\H主机名  
&ensp;&ensp;\w当前工作目录&ensp;&ensp;&ensp;&ensp;&ensp;\W当前工作目录基名   
&ensp;&ensp;\24小时时间格式&ensp;&ensp;&ensp;&ensp;&ensp;\T12小时时间格式  
&ensp;&ensp;\！命令历史数&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;\ #开机后命令历史数      

## 执行命令  
>- 输入命令后回车    
>- 提请shell程序找到键入命令所对应的可执行程序或代码，并由其分析后提交给内核分配资源将其运行起来   
>- 在shell中可执行的命令有两类   
&ensp;&ensp;内部命令：由shell自带的，而且通过某命令形势提供   
&ensp;&ensp;help&ensp;&ensp;内部命令列表   
&ensp;&ensp;enable&ensp;&ensp;cmd启用内部命令  
&ensp;&ensp;enable&ensp;-n&ensp;cmd&ensp;禁用内部命令  
&ensp;&ensp;enable&ensp;=-n&ensp;查看所有禁用的内部命令  
&ensp;&ensp;外部命令：在文件系统路径下有对应的可执行程序文件  
&ensp;&ensp;查看路径：which&ensp;-a&ensp;|--skip-alias；whereis   
>- 区别指定的命令是内部或外部命令type&ensp;COMMAND  
   
## 执行外部命令   
- Hash缓存表   
系统初始hash表为空，当外部命令执行时，默认会从PATH路径下寻找该命令，找到后会将这条命令的路径记录到hash表中，当再次使用该命令时，shell解释器首先会查看hash表，存在将执行之，如果不存在，将会去PATH路径下寻找，利用hash缓存表可大大提高命令的调用速率   
 - hash常见用法  
hash&ensp;&ensp;显示hash缓存   
hash&ensp;-l&ensp;显示hash缓存，可作为输入使用  
hash&ensp;-p&ensp;path&ensp;name&ensp;将命令全路径path起别名为name   
hash&ensp;-t&ensp;name&ensp;打印缓存中name的路径   
hash&ensp;-d&ensp;name&ensp;清除name缓存   
hash&ensp;-r&ensp;清除缓存   
## 命令别名   
- 显示当前shell进程所有可能的命令别名   
&ensp;&ensp;alias  
- 定义别名NAME，其相当于执行命令VALUE  
&ensp;&ensp;alias&ensp;&ensp;NAME='VALUE'
- 在命令中定义的别名，仅对当前shell进程有效   
- 如果想永久有效，要定义在配置文件中  
&ensp;&ensp;&ensp;仅对当前用户：~/.bashrc   
&ensp;&ensp;&ensp;对所有用户有效：/etc/bashrc  
- 编辑配置给出的新配置不会立即生效  
- bash进程重新读取配置文件  
&ensp;source /path/to/config_file  
&ensp;.&ensp;/path/to/config_file  
- 撤销别名：unaias  
&ensp;&ensp;unalias [-a]name [name...]
&ensp;&ensp;-a&ensp;取消所有别名   
- 如果别名同原命令同名，如果要执行原命令，可使用  
&ensp;&ensp;\ALIASNAME  
&ensp;&ensp;"ALIASNAME"  
&ensp;&ensp;'ALIASNAME'  
&ensp;&ensp;command&ensp;ALLASNAME   
&ensp;&ensp;/path/commmand

## 命令格式  
- COMMANDV&ensp;[OPTIONS...][ARGUMENTS...]   
&ensp;&ensp;&ensp;选项：用于启用或关闭命令的某个或某些功能  
&ensp;&ensp;&ensp;短选项：&ensp;-c&ensp;例如：&ensp;-l，&ensp;-h  
&ensp;&ensp;&ensp;长选项：&ensp;&ensp;--word&ensp;例如：  --all,&ensp;--human-readable  
&ensp;&ensp;&ensp;参数：命令的作用对象，比如文件名，用户名等   
- 注意：    
&ensp;&ensp;多个选项以及多参数和命令之间使用空白字符分割  
&ensp;&ensp;取消和结束命令执行：Ctcl+c ,   Ctrl+d   
&ensp;&ensp;多个命令可以用；符号分开   
&ensp;&ensp;一个命令可以用\分成多行


## 日期和时间   
- Linux的两种时钟   
&ensp;&ensp;系统时钟：由Linux内核通过CPU的工作频率进行的   
&ensp;&ensp;硬件时钟：主板
- 相关命令    
&ensp;&ensp;date&ensp;&ensp;显示和设置系统时间  
&ensp;&ensp;date&ensp;+%s   
&ensp;&ensp;date&ensp;&ensp;-d@1509536033  
&ensp;&ensp;hwclock,clock:显示硬件时钟    
&ensp;&ensp;-s,&ensp;&ensp;--hctosys&ensp;以硬件时钟为准，校正系统时钟  
&ensp;&ensp;-w,&ensp;&ensp;--systohc&ensp;&ensp;以系统时间为准，校正硬件时钟
- 时区：&ensp;/etc/localtime  
- 显示日历：cal-y   

## 简单命令   
- 关机：halt,poweroff   
- 重启：reboot   
&ensp;&ensp;-f:强制，不调用shutdown   
&ensp;&ensp;-p:切断电源   
- 关机或重启：shutdown  
&ensp;shutdown[OPTION]...[TIME][MESSAGE]  
&ensp;-r:reboot  
&ensp;-h:halt  
&ensp;-c:cancel  
&ensp;TIME:无指定，默认相当于+1（CentOs7）  
&ensp;now:立刻，相当于+0   
&ensp;+m：相对时间表示法，几分钟之后；例如+3  
&ensp;hh:mm：绝对时间表示，指具体时间   
- 用户登陆信息查看命令：  
&ensp;whoami:显示当前登陆有效用户  
&ensp;who：系统当前所有的登陆会话  
&ensp;w：系统当前所有的登陆会话及所做的操作   
- nano&ensp;文本编辑   
- screen命令：   
&ensp;创建新screen会话   
&ensp;&ensp;&ensp;screen -S [SESSION]   
&ensp;加入screen -X[SESSION]
&ensp;&ensp;&ensp;screen -X [SESSION]
&ensp;退出并关闭screen会话  
&ensp;&ensp;&ensp;exit    
&ensp;剥离当前screen会话   
&ensp;&ensp;&ensp;Ctrl+a，d   
&ensp;显示所有已经打开的screen会话    
&ensp;&ensp;&ensp;screen -ls    
&ensp;恢复某screeen&ensp;-r [SESSION]

   
      
## 简单命令  
- echo命令  
- 功能：显示字符  
- 语法：echo&ensp;[-neE][字符串]  
- 说明：echo会将输入的字符串送往标准输出。输出的字符串间以空白字符隔开，并在最后加上换行号  
- 选项：
&ensp;&ensp;-E&ensp;&ensp;（默认）不支持\解释功能  
&ensp;&ensp;-n&ensp;&ensp;不自动换行   
&ensp;&ensp;-e&ensp;&ensp;启用\字符的解释功能   
- 显示变量  
&ensp;&ensp;echo&ensp;&ensp;"$VAR_NAME"&ensp;&ensp;变量会替换，弱引用    
&ensp;&ensp;echo&ensp;&ensp;'$VAR_NAME'&ensp;&ensp;变量不会替换，强引用   
   
- 启用命令选项-e，若字符串中出现以下字符，则特别加以处理，而不会将它当成一般文字输出  
\a&ensp;发出警告声  
\b&ensp;退格键  
\c&ensp;最后不加上换行符号  
\n&ensp;换行且光标移动行首     
\r&ensp;回车，即光标移至行首，但不换行  
\t&ensp;插入tad  
\\&ensp;插入\字符  
\&ensp;0nnn&ensp;插入nnn&ensp;（八进制）所代表的ASCII字符  
## 字符集和编码  
- ASCLL码：计算机内部，所有信息最终都是一个二进制值。  
- Unicode:用于表示世界上所有语言中的所有字符。  
- Unicode编码方案：  
&ensp;&ensp;&ensp;UTF-8：变长，1到4个字节  
&ensp;&ensp;&ensp;UTF-16：变长，2或4个字节  
&ensp;&ensp;&ensp;UTF-32：固定长度，4个字节  
   
##获得帮助  
- 获取帮助的能力决定技术的能力！  
- 多层次的帮助  
&ensp;whatis  
&ensp;command&ensp;--help  
&ensp;man&ensp;and&ensp;info  
&ensp;/usr/share/doc/  
&ensp;Red&ensp;Hat&ensp;documentation  
&ensp;其他网站的搜索  
   
## 命令history  
&ensp;&ensp;-history&ensp;[-c]&ensp;[-d&ensp;offset]&ensp; [n]   
&ensp;&ensp;-history&ensp;-anrw [filename]   
&ensp;&ensp;-hiastory&ensp;-ps&ensp;&ensp;ary [arg...]   
&ensp;&ensp;-c:&ensp;&ensp;清空命令历史  
&ensp;&ensp;-d&ensp;&ensp;offset:&ensp;&ensp;删除历史中指定的第offset个命令   
&ensp;&ensp;n:&ensp;&ensp;显示最近的n条历史   
&ensp;&ensp;-a:&ensp;&ensp;追加本次会话新执行的命令历史列表至历史文件   
&ensp;&ensp;-r：&ensp;读历史文件附加到历史列表   
&ensp;&ensp;-w：&ensp;保存历史列表到指定的历史文件   
&ensp;&ensp;-n：&ensp;读历史文件中未读过的行到历史列表  
&ensp;&ensp;-p：&ensp;展开历史参数成多行，但不存在历史列表中   
&ensp;&ensp;-s:&ensp;展开历史参数成一行，附加在历史列表后    
   
## help和-h选项  
- 显示用法总结和参数列表  
- 使用的大多数，但非所有的  
- 示例：  
&ensp;&ensp;&ensp;date --help  
&ensp;&ensp;&ensp;&ensp;&ensp;Usage:date[OPTION]...[FORMAT]&ensp;or:date&ensp;[-u|--utc|--universal][MMDDhhmm][CC]YY][.ss]]  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;[&ensp;]表示可选项    
&ensp;&ensp;CAPS或<>表示变化的数据   
&ensp;&ensp;...表示一个列表    
&ensp;&ensp;x|y|z&ensp;&ensp;的意思是”x或y或z”  
&ensp;&ensp;&ensp;&ensp;-abc的意思是&ensp;-a&ensp;-b&ensp;&ensp;-c   
&ensp;&ensp;{表示分组}    
    
## bash的快捷键   
- Ctrl+l&ensp;清屏，相当于clear命令   
- Ctrl+o&ensp;执行当前命令，并重新显示本命令   
- Ctrl+s&ensp;阻止屏幕输出，锁定   
- Ctrl+q&ensp;允许屏幕输出  
- Ctrl+z&ensp;挂起命令   
    
## 文件名规则 
- 蓝色-->&ensp;&ensp;&ensp;目录   
- 绿色-->&ensp;&ensp;&ensp;可执行文件  
- 红色-->&ensp;&ensp;&ensp;压缩文件  
- 浅蓝色-->&ensp;连接文件  
- 灰色-->&ensp;&ensp;&ensp;其他文件  
   
## 更改目录  
- cd&ensp;&ensp;改变目录  
使用绝对或相对路径：  
&ensp;&ensp;cd/home/wang/  
&ensp;&ensp;cd&ensp;home/wang  
&ensp;&ensp;切换至父目录：&ensp;&ensp;&ensp;cd..
&ensp;&ensp;切换至当前用户主目录：&ensp;&ensp;cd  
&ensp;&ensp;切换至以前的工作目录：&ensp;cd&ensp;-
- 选项：&ensp;-P
- 相关的环境变量：  
&ensp;&ensp;PWD：当前目录路径   
&ensp;&ensp;OLDPWD：上一次目录路径
