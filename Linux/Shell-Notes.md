# shell 学习笔记

[博客链接](https://blog.csdn.net/weixin_42313749/article/details/120524768?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169841398716800215055800%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169841398716800215055800&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-120524768-null-null.142^v96^pc_search_result_base4&utm_term=shell&spm=1018.2226.3001.4187)

## 什么是 shell
就是Linux脚本命令</br>
shell脚本一般以 .sh 结尾


## 常用代码
```shell
chmod o+x test.sh   # 赋予test.sh 脚本权限
./test.sh           #运行test.sh 脚本
```

## Shell中的变量
### 常见的3种变量
Shell编程中变量分为三种，分别是系统变量、环境变量和用户变量，Shell变量名在定义时，首个字符必须为字母（a-z，A-Z），不能以数字开头，中间不能有空格，可以使用下划线（_），不能使用（-），也不能使用标点符号等。

### Demo样例
```shell
(base) [root@localhost ~]# a=18
(base) [root@localhost ~]# echo $a
18
```
### 系统变量
Shell常见的变量之一系统变量，主要是用于对参数判断和命令返回值判断时使用，系统变量详解如下：

```
$0 		当前脚本的名称；
$n 		当前脚本的第n个参数,n=1,2,…9；
$* 		当前脚本的所有参数(不包括程序本身)；
$# 		当前脚本的参数个数(不包括程序本身)；
$? 		令或程序执行完后的状态，返回0表示执行成功；
$$ 		程序本身的PID号。
```

### 环境变量
Shell常见的变量之二环境变量，主要是在程序运行时需要设置，环境变量详解如下：

```
PATH  		命令所示路径，以冒号为分割；
HOME  		打印用户家目录；
SHELL 		显示当前Shell类型；
USER  		打印当前用户名；
ID    		打印当前用户id信息；
PWD   		显示当前所在路径；
TERM  		打印当前终端类型；
HOSTNAME    显示当前主机名；
PS1         定义主机命令提示符的；
HISTSIZE    历史命令大小，可通过 HISTTIMEFORMAT 变量设置命令执行时间;
RANDOM      随机生成一个 0 至 32767 的整数;
HOSTNAME    主机名
```

### 用户变量
常见的变量之三用户变量，用户变量又称为局部变量，主要用在Shell脚本内部或者临时局部使用，系统变量详解如下：
```
a=rivers 				       自定义变量A；
Httpd_sort=httpd-2.4.6-97.tar  自定义变量N_SOFT；
BACK_DIR=/data/backup/         自定义变量BACK_DIR；
IPaddress=10.0.0.1			   自定义变量IP1；
```

### if 语句
If条件判断语句，通常以if开头，fi结尾。也可加入else或者elif进行多条件的判断

```
# 单分支语句 ---比较大小
	if (条件表达式);then
		语句1
	fi

# 双分支if 语句
	if (表达式)
		语句1
	else
		语句2
	fi

# 多支条件语句 ---判断成绩
	if (表达式)
		语句1
	elif
		语句2
	elif
		语句2
	fi  
```

### 常见逻辑判断运算符号
```
-f	 	判断文件是否存在 eg: if [ -f filename ]；
-d	 	判断目录是否存在 eg: if [ -d dir     ]；
-eq		等于，应用于整型比较 equal；
-ne		不等于，应用于整型比较 not equal；
-lt		小于，应用于整型比较 letter；
-gt		大于，应用于整型比较 greater；
-le		小于或等于，应用于整型比较；
-ge 	大于或等于，应用于整型比较；
-a		双方都成立（and） 逻辑表达式 –a 逻辑表达式；
-o		单方成立（or） 逻辑表达式 –o 逻辑表达式；
-z		空字符串；
-x      是否具有可执行权限
||      单方成立；
&&      双方都成立表达式。
```









