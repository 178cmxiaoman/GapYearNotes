# Linux 基础学习笔记
笔者最近在学习 Linux 系统的过程中，遇到了各种不同需求下的代码，因此本文特地做了一个总结，以供日后来复习、查询，同时也希望跟笔者一样的初学者可以通过本文获得一定的帮助。
## 一、常用 Linux 命令
对于Linux初学者来说，掌握一些常用的Linux命令，就好比刚出生的小孩第一次学会如何走路，是万物的基础。本章中将总结给出常见的 Linux 命令。

### 1.1 文件和目录管理
- `ls`：列出目录内容
- `cd`：改变目录
- `pwd`：显示当前目录
- `mkdir`：创建新目录
- `rmdir`：删除空目录
- `cp`：复制文件或目录
- `mv`：移动或重命名文件或目录
- `rm`：删除文件或目录
- `touch`：创建空文件或修改文件时间戳

### 1.2 文本处理
- `cat`：显示文件内容
- `more`：分页显示文本文件
- `less`：分页显示文本文件（更高级）
- `grep`：文本搜索
- `sed`：流编辑器
- `awk`：模式扫描和文本处理语言

### 1.3 系统信息和管理
- `top`：显示当前进程
- `ps`：显示用户进程
- `kill`：结束进程
- `df`：磁盘空间使用情况
- `du`：目录空间使用情况
- `free`：显示内存和交换区使用情况
- `uptime`：显示系统运行时间和平均负载

### 1.4 网络和通信
- `ping`：检测网络连接
- `ifconfig`：配置和显示网络接口参数
- `ssh`：安全远程登录
- `scp`：安全文件复制
- `wget`：从网络下载文件
- `curl`：数据传输工具，支持多种协议

### 1.5 文件权限和所有权
- `chmod`：更改文件权限
- `chown`：更改文件所有者
- `chgrp`：更改文件所属组


## 二、Linux 中的压缩与解压命令
Linux中对于文件的管理，最常见的就是压缩和解压操作，同时也要掌握不同的文件格式所对应的命令。掌握这些基本命令，可以在日常工作中大大提高文件处理的效率。以下给出一些常见的文件格式。

### 2.1 gzip/gunzip
- `gzip <filename>`：压缩文件，生成`.gz`文件
- `gunzip <filename.gz>`：解压`.gz`文件

### 2.2 tar
- `tar -cvf <archive.tar> <directory>`：创建不压缩的tar包
- `tar -xvf <archive.tar>`：解压tar包
- `tar -czvf <archive.tar.gz> <directory>`：创建gzip格式的压缩tar包
- `tar -xzvf <archive.tar.gz>`：解压gzip格式的tar包
- `tar -cjvf <archive.tar.bz2> <directory>`：创建bzip2格式的压缩tar包
- `tar -xjvf <archive.tar.bz2>`：解压bzip2格式的tar包

### 2.3 bzip2/bunzip2
- `bzip2 <filename>`：压缩文件，生成`.bz2`文件
- `bunzip2 <filename.bz2>`：解压`.bz2`文件

### 2.4 zip/unzip
- `zip <archive.zip> <filename>`：压缩文件或目录到zip包
- `unzip <archive.zip>`：解压zip包

### 2.5 rar/unrar (如果已安装)
- `rar a <archive.rar> <filename>`：压缩文件或目录到rar包
- `unrar x <archive.rar>`：解压rar包

### 2.1 7z (如果已安装7z)
- `7z a <archive.7z> <filename>`：压缩文件或目录到7z包
- `7z x <archive.7z>`：解压7z包





## 三、Linux 中常用的关于 Python 的命令和代码
在 Linux 中经常需要运行python代码，尤其是跑深度学习的同学。本节总结了与Python相关的常用命令和代码片段涉及到的多种场景，如安装Python、管理Python环境、运行Python脚本等。

### 3.1 安装 Python
- `sudo apt-get install python3`：在基于Debian的系统（如Ubuntu）中安装Python 3
- `sudo yum install python3`：在基于RPM的系统（如CentOS）中安装Python 3

### 3.2 管理 Python 环境
- `python3 -V` 或 `python3 --version`：检查Python版本
- `alias python=python3`：将`python`命令指向`python3`（临时）

### 3.3 使用 pip 管理包
- `pip3 install <package_name>`：安装一个Python包
- `pip3 uninstall <package_name>`：卸载一个Python包
- `pip3 list`：列出已安装的Python包
- `pip3 freeze > requirements.txt`：生成依赖文件
- `pip3 install -r requirements.txt`：根据依赖文件安装包

### 3.4 运行 Python 脚本
- `python3 <script_name.py>`：运行Python脚本
- `python3 -m <module_name>`：运行Python模块

### 3.5 Python 交互式解释器
- `python3`：启动Python 3交互式解释器

### 3.6 Python 一行代码示例
- `python3 -c 'print("Hello, World!")'`：在命令行中执行一行Python代码
- `python3 -m http.server`：启动一个简单的HTTP服务器

### 3.7 创建和激活虚拟环境
- `python3 -m venv <env_name>`：创建一个虚拟环境
- `source <env_name>/bin/activate`：激活虚拟环境（Bash）
- `deactivate`：退出虚拟环境

### 3.8 Jupyter Notebook
- `pip3 install jupyter`：安装Jupyter Notebook
- `jupyter notebook`：启动Jupyter Notebook



## 四、Linux 中常用的进程管理命令

### 4.1 查看进程
- `ps`：显示当前进程的快照
- `ps aux`：显示所有进程的详细信息
- `top`：实时显示进程信息和系统资源使用情况
- `htop`（如果已安装）：比top更高级的工具，提供更丰富的信息和更易用的界面

### 4.2 控制进程
- `kill <pid>`：发送SIGTERM信号来结束进程（pid为进程ID）
- `kill -9 <pid>`：发送SIGKILL信号来强制结束进程
- `killall <process_name>`：结束所有名为process_name的进程
- `pkill <pattern>`：基于模式匹配结束进程

### 4.3 管理后台进程
- `<command> &`：在后台运行命令
- `bg`：将一个已停止的后台任务继续运行
- `fg`：将后台任务移至前台
- `jobs`：显示当前的后台任务

### 4.4 系统服务管理
- `systemctl start <service>`：启动服务
- `systemctl stop <service>`：停止服务
- `systemctl restart <service>`：重启服务
- `systemctl status <service>`：查看服务状态

### 4.5 查看和控制进程资源使用
- `nice`：启动进程并设置优先级
- `renice`：更改已运行进程的优先级
- `ulimit`：控制shell启动进程的资源限制

### 4.6 系统性能和进程监控
- `vmstat`：显示虚拟内存统计信息
- `iostat`：显示CPU和输入/输出统计信息
- `lsof`：列出打开的文件和使用它们的进程

## 五、结语
希望本文能对你有所帮助！

<!-- 头像 -->
![](https://raw.githubusercontent.com/178cmxiaoman/PicGo-repository/main/GapYearNotes/head.jpg)