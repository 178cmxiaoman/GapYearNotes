# Linux 学习笔记
[Linux操作系统详细介绍](https://blog.csdn.net/m0_52051132/article/details/128362191?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169822650416800182121857%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=169822650416800182121857&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-1-128362191-null-null.142^v96^pc_search_result_base4&utm_term=linux%E5%92%8Ccontes%E5%85%B3%E7%B3%BB&spm=1018.2226.3001.4187)

[Linux入门参考博客教程(本文主要参考)](https://blog.csdn.net/leah126/article/details/131558171?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169821543916800225537867%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169821543916800225537867&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-1-131558171-null-null.142^v96^pc_search_result_base4&utm_term=linux%E6%95%99%E5%AD%A6&spm=1018.2226.3001.4187)


## 常用Linux命令：
```
cd		进入目录
cd..	回到上一级目录
pwd		显示当前目录的路径
ls		列出当前目录中所有文件
ll		列出当前目录中所有文件（更为详细）
cat     查看文件
touch	新建一个文件，例如touch test.txt
rm		删除一个文件，例如rm test.txt
mkdir	新建一个文件夹，例如mkdir test
rm -r	删除一个文件夹，例如rm -r src
mv		移动文件，例如mv index.html src
reset	重新初始化终端
clear	清屏
history	查看历史命令
help	查看命令历史
exit	退出
#		注释
pwd     显示当前工作目录的绝对路径
df -lh  查看内存
```

查看centos具体版本 

```
cat /etc/centos-release
```

mv 移动文件与目录或重命名
```
# 重命名
mv xiyou/dssz/suwukong.txt xiyou/dssz/houge.txt

# 移动文件
mv xiyou/dssz/houge.txt ./
```
echo输出内容到控制台
```
echo “hello\tworld”
echo -e “hello\tworld” # -e支持反斜线控制的字符转换
```

## 压缩与解压
### .gz文件
gzip压缩(压缩成xxx.gz文件)
```
gzip lnTest.txt
```

gunzip解压缩文件(解压xxx.gz压缩包)
```
gunzip lnTest.txt.gz
```
---
### .zip文件
zip压缩(压缩成xxx.zip文件)
```
zip 压缩文件名.zip  源文件

# 压缩文件
zip lnTest.zip lnTest.txt

# -r 压缩文件夹
zip -r  nginx1.zip nginx-1.21.6
```

unzip解压(解压xxx.zip压缩包)
```
unzip lnTest.zip

# -d 指定解压后文件的存放目录
unzip lnTest.zip -d /opt
```
### .tar.gz文件
tar压缩(压缩成xxx.tar.gz文件)
```
tar -zcvf 打包的文件名.tar.gz [源文件]

# 多个文件打包
tar -zcvf houma.tar.gz houge.txt bailongma.txt

# 打包文件夹
tar -zcvf xiyou.tar.gz xiyou/
```

tar解压(解压xxx.tar.gz压缩包)
```
# 解压到当前目录
tar -zxvf houma.tar.gz
# -C 解压到某个目录下
tar -zxvf xiyou.tar.gz -C /opt
```
### 其他压缩包链接
[.7z压缩参考博客](https://blog.csdn.net/surp2011/article/details/118269713?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169822380416777224435902%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169822380416777224435902&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-2-118269713-null-null.142^v96^pc_search_result_base4&utm_term=linux%E5%8E%8B%E7%BC%A97z&spm=1018.2226.3001.4187)

## 磁盘查看和分区类
du 查看文件和目录占用的磁盘空间
```
# 查看当前文件总占用
du -sh 

# 当前目录下所有文件磁盘占用
du -sh *

# 某文件夹下所有文件的磁盘占用
du -sh /home/*

# -c 显示总和
du -csh /home/*
```
df 查看磁盘空间使用情况
```
df -h
```

Linux中每个分区都是用来组成整个文件系统的一部分，它在用一种叫做“挂载”的处理方法，它整个文件系统中包含了一整套的文件和目录，并将一个分区和一个目录联系起来，要载入的那个分区将使它的存储空间在这个目录下获得。

lsblk 查看设备挂载情况
```
lsblk

# 查看详细的设备挂载情况，显示文件系统信息
lsblk -f 
```

## 进程管理类
```
ps -ef：列出所有进程的详细信息。

ps aux：与ps -ef类似，但是显示的是所有用户的进程信息。
```

ps -ef 显示信息说明
```
UID     用户 ID
PID     进程 ID
PPID    父进程 ID
C       CPU 用于计算执行优先级的因子。数值越大，表明进程是 CPU 密集型运算，执行优先级会降低；数值越小，表明进程是 I/O 密集型运算，执行优先级会提高
STIME   进程启动的时间
TTY     完整的终端名称
TIME    CPU 时间
CMD     启动进程所用的命令和参数
```
ps aux 显示信息说明：
```
USER    该进程是由哪个用户产生的
PID     进程的 ID 号
%CPU    该进程占用 CPU 资源的百分比，占用越高，进程越耗费资源；
%MEM    该进程占用物理内存的百分比，占用越高，进程越耗费资源；
VSZ     该进程占用虚拟内存的大小，单位 KB；
RSS     该进程占用实际物理内存的大小，单位 KB；
TTY     该进程是在哪个终端中运行的。对于 CentOS 来说，tty1 是图形化终端，
tty2-tty6 是本地的字符界面终端。pts/0-255 代表虚拟终端。
STAT    进程状态。常见的状态有：R：运行状态、S：睡眠状态、T：暂停状态、Z：僵尸状态、s：包含子进程、l：多线程、+：前台显示
START   该进程的启动时间
TIME    该进程占用 CPU 的运算时间，注意不是系统时间
COMMAND 产生此进程的命令名

```
grep 查询进程
```
ps -ef | grep java      查询java进程
ps -ef | grep python    查询python进程
ps -ef | grep python3   查询python3进程

```
kill 终止进程
```
kill -9 5102    终止pid为5102的进程
killall firefox 终止进程名为firefox的进程
```
top 实时监控系统进程状态
```
top
```

pstree 查看进程树
```
# 显示进程的 PID
pstree -p
# 显示进程的所属用户
pstree -u
```

## 软件包管理
BPM
```
rpm -i 包名.rpm     安装
rpm -v 包名.rpm     显示详细信息
rpm -h 包名.rpm     进度条

rpm -ivh 包名.rpm
```
## 
rpm -qa |grep firefox

YUM仓库配置
```
rpm -qa|grep yum    查看yum是否安装

yum install 包名    安装包
```
[yum详细博客链接](https://blog.csdn.net/qq_36299025/article/details/90901055?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169822191516800197089531%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169822191516800197089531&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-90901055-null-null.142^v96^pc_search_result_base4&utm_term=yum&spm=1018.2226.3001.4187)

## ubuntu18.04 查看cuda和cudnn版本
1.查看cuda版本
cat /usr/local/cuda/version.txt