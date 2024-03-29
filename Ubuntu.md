# 启动与关闭 #
关机  
挂起：保存住数据，恢复比较快
# 更多操作 #
硬件参数设置，先关机再设置  
状态栏  
全屏显示  
# 快照与系统恢复  
重装系统和拍摄恢复快照

# 主要目录速查表 
- /：根目录，一般根目录下只存放目录，在 linux 下有且只有一个根目录，所有的东西都是从这里开始

- 当在终端里输入 /home，其实是在告诉电脑，先从 /（根目录）开始，再进入到 home 目录
 
- /bin、/usr/bin：可执行二进制文件的目录，如常用的命令 ls、tar、mv、cat 等

- /boot：放置 linux 系统启动时用到的一些文件，如 linux 的内核文件：/boot/vmlinuz，系统引导管理器：/boot/grub

- /dev：存放linux系统下的设备文件，访问该目录下某个文件，相当于访问某个设备，常用的是挂载光驱mount /dev/cdrom/mnt
 
- /etc：系统配置文件存放的目录，不建议在此目录下存放可执行文件，重要的配置文件有
 
- /etc/inittab
- /etc/fstab
- /etc/init.d
- /etc/X11
- /etc/sysconfig
- /etc/xinetd.d

- /home：系统默认的用户家目录，新增用户账号时，用户的家目录都存放在此目录下表示当前用户的家目录
 
- ~edu 表示用户 edu 的家目录
 
- /lib、/usr/lib、/usr/local/lib：系统使用的函数库的目录，程序在执行过程中，需要调用一些额外的参数时需要函数库的协助
 
- /lost+fount：系统异常产生错误时，会将一些遗失的片段放置于此目录下
 
- /mnt: /media：光盘默认挂载点，通常光盘挂载于 /mnt/cdrom 下，也不一定，可以选择任意位置进行挂载
 
- /opt：给主机额外安装软件所摆放的目录
 
- /proc：此目录的数据都在内存中，如系统核心，外部设备，网络状态，由于数据都存放于内存中，所以不占用磁盘空间，比较重要的文件有：/proc/cpuinfo、/proc/interrupts、/proc/dma、/proc/ioports、/proc/net/*等
 
- /root：系统管理员root的家目录
 
- /sbin、/usr/sbin、/usr/local/sbin：放置系统管理员使用的可执行命令，如 fdisk、shutdown、mount 等。与 /bin 不同的是，这几个目录是给系统管理员 root使用的命令，一般用户只能"查看"而不能设置和使用
 
- /tmp：一般用户或正在执行的程序临时存放文件的目录，任何人都可以访问，**重要数据不可放置在此目录下** 
 -/srv：服务启动之后需要访问的数据目录，如 www 服务需要访问的网页数据存放在 /srv/www 内 
- /usr：应用程序存放目录

- /usr/bin：存放应用程序

- /usr/share：存放共享数据

- /usr/lib：存放不能直接运行的，却是许多程序运行所必需的一些函数库文件

- /usr/local：存放软件升级包

- /usr/share/doc：系统说明文件存放目录

- /usr/share/man：程序说明文件存放目录

- /var：放置系统执行过程中经常变化的文件

- /var/log：随时更改的日志文件

- /var/spool/mail：邮件存放的目录

- /var/run：程序或服务启动后，其 PID 存放在该目录下


序号	命令	对应英文	作用
01	ls	list	查看当前文件夹下的内容  
02	pwd	print work directory	查看当前所在的文件夹  
03	cd[目录名]	change directory	切换文件夹  
04	touch[文件名]	touch	如果文件不存在，新建文件  
05	mkdir[目录名]	make directory	创建目录  
06	rm[文件名]	remove	删除指定文件名  
07	clear	clear	清屏
小技巧

ctrl + shift + = 放大终端窗口的字体显示
ctrl + - 缩小终端窗口的字体显示
按 上／下 光标键可以在曾经使用过的命令之间来回切换
>如果想要退出选择，并且不想执行当前选中的命令，可以按 ctrl + c

>>自动补全 : 在敲出 文件／目录／命令 的前几个字母之后，按下 tab 键
如果输入的没有歧义，系统会自动补全
如果还存在其他 文件／目录／命令，再按一下 tab 键，系统会提示可能存在的命令
# 终端命令格式 #
终端命令：command [options] parameters  
查阅命令帮助信息：-help -man help(说明手册）
#Ubuntu的文件和目录常用命令
3.1. 查看目录内容  
3.1.1 ls 命令说明  
ls 是英文单词 list 的简写，其功能为列出目录的内容，是用户最常用的命令之一，类似于 DOS 下的 dir 命令  
## Linux 下文件和目录的特点 ##

Linux 文件 或者 目录 名称最长可以有 256 个字符  
以 **. 开头的文件为隐藏文件**，需要用** -a 参数**才能显示  
. 代表当前目录  
… 代表上一级目录  
3.1.2 ls 通配符的使用  
  
*	：   代表任一个数的字符  
？	：    代表任意一个字符，至少1个  
[]	 ：  表示可以匹配字符组中的任意一个  
[abc]：	    匹配a、b、c中的任意一个 
[a-f]	：    匹配从a到f范围内的任意一个字符  
3.2. 切换目录  
3.2.1 cd  
cd 是英文单词 change directory 的简写，其功能为更改当前的工作目录，也是用户最常用的命令之一  
 **Linux 所有的 目录 和 文件名 都是大小写敏感的**


cd	切换到当前用户的主目录(/home/用户目录)  
cd ~	切换到当前用户的主目录(/home/用户目录)  
cd .	保持在当前目录不变  
cd …	切换到上级目录  
cd -	可以在最近两次工作目录之间来回切换  
3.2.2 相对路径和绝对路径  
相对路径 在输入路径时，最前面不是 / 或者 ~，表示相对 当前目录 所在的目录位置   
绝对路径 在输入路径时，最前面是 / 或者 ~，表示从 根目录/家目录 开始的具体目录位置  
3.3 创建和删除操作  
3.3.1 touch 创建文件或修改文件时间    
如果文件 不存在，可以创建一个空白文件    
如果文件 已经存在，可以修改文件的末次修改日期    
3.3.2 mkdir 创建一个新的目录   

-p	可以递归创建目录  
新建目录的名称** 不能与当前目录中已有的目录或文件同名  **

3.3.3 rm 删除文件或目录  
使用 rm 命令要小心，因为文件删除后不能恢复  


-f	强制删除，忽略不存在的目录，无需提示  
-r	递归删除目录下的内容，删除文件时必须加此参数  
3.4 拷贝和移动文件  
序号	命令	对应英文	作用  
01	tree [目录名]	tree	以树状图列出文件目录结构  
02	cp 源文件 目标文件	copy	复制文件或者目录  
03	mv 源文件 目标文件	move	移动文件或者目录／文件或者目录重命名  
3.4.1 tree  
tree 命令可以以树状图列出文件目录结构   
选项	含义
-d	只显示目录  
3.4.2 cp  
cp 命令的功能是将给出的 文件 或 目录 复制到另一个 文件 或 目录 中，相当于 DOS 下的 copy 命令  

-i	覆盖文件前提示  
-r	若给出的源文件是目录文件，则 cp 将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名  
3.4.3 mv  
mv 命令可以用来 移动 文件 或 目录，也可以给 文件或目录重命名
选项	含义  
-i	覆盖文件前提示  
3.5. 查看文件内容  
序号	命令	对应英文	作用  
01	cat 文件名	concatenate	查看文件内容、创建文件、文件合并、追加文件内容等功能  
02	more 文件名	more	分屏显示文件内容  
03	grep 搜索文本 文件名	grep	搜索文本文件内容  
3.5.1 cat  
cat 命令可以用来 查看文件内容、创建文件、文件合并、追加文件内容 等功能  

cat 会一次显示所有的内容，查询数量较少或者需要对文件执行特定操作时使用  

选项	含义  
-b	对非空输出行编号  
-n	对输出的所有行编号  
Linux 中还有一个 nl 的命令和 cat -b 的效果等价  

例：
**cat [n,v,i] as 123.txt**

//高亮123.txt中含有as的文本
n：**显示高亮部分配对的行号**  
v：（**取反）非高亮部分配对的行号**  
i:对选定条件的额内容不区分大小写比如"Hello JAVA"=="hello java"  
1
2
3
4
5
6
7
3.5.2 more    
more 命令可以用于分屏显示文件内容，每次只显示一页内容    
适合于 查看内容较多的文本文件    
使用 more 的操作键：    

操作键	功能  
空格键	显示手册页的下一屏  
Enter 键	一次滚动手册页的一行  
b	回滚一屏  
f	前滚一屏  
q	退出  
/word	搜索 word 字符串  
3.5.3 grep  
Linux 系统中 grep 命令是一种文本搜素工具  
grep允许对文本文件进行模式查找，所谓模式查找，又被称为正则表达式，
选项	含义  
-n	显示匹配行及行号  
-v	显示不包含匹配文本的所有行（相当于求反）  
-i	忽略大小写  
常用的两种模式查找  
参数	含义  
^a	行首，搜寻以 a 开头的行  
hzh$	行尾，搜寻以 hzh 结束的行  
3.6. 其他  
3.6.1 echo 文字内容  
-会在终端中输出你所输入的内容比如 echo hello,输出hello常和重定向配合使用  

3.6.2 重定向 > 和 >>  
Linux 允许将命令执行结果 重定向到一个文件  
将本应显示在终端上的内容 输出／追加 到指定文件中  
其中   

“>” 表示输出，会覆盖文件原有的内容  
“>>” 表示追加，会将内容追加到已有文件的末尾  
3.6.3 管道  |
Linux 允许将 一个命令的输出 可以通过管道 做为另一个命令的输入
可以理解现实生活中的管子，管子的一头塞东西进去，另一头取出来，这里 | 的左右分为两端，左端塞东西（写），右端取东西（读）
常用的管道命令有：

more：分屏显示内容  
grep：在命令执行结果的基础上查询指定的文本
#远程管理 #
4.1关机与重启
shutdown [选项][时间] 关机/重启（加r)
shutdown -r now 立即重启

注意，一般远程服务器最好是选择重启

4.2网卡与ip
网卡是一个专门的负责网络通讯的硬件设备
IP地址是设置再网卡上的地址信息（是唯一的）

4.3查看或配置网卡信息
ifconfig 查看或配置计算机当前的网卡配置信息
如：ifconfig |grep inet 快速查找IP地址
127.0.0.1 被称为本地回环/环回地址一般用来测试本地网卡是否正常

ping ip地址 检测到目标IP地址的连接是否正常

