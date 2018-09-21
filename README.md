# 9yue21Linux基础
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
