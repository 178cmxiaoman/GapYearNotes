# GitHub学习笔记

## Git初始化操作
首先要在github上创建好仓库
```
echo "name" >> README.md
git init
git add README.md
git commit -m "备注"
git branch -M main
git remote add origin git@github.com:178cmxiaoman/GapYearNotes.git
git remote add git push -u origin main
```

## 对于以及初始化过的仓库
```
git remote add origin git@github.com/....git
git branch -M main
git push -u orgin main
```


## 常用git指令
```
#在当前目录新建一个Git代码库
git init

#克隆一个项目和它的整个代码历史（版本信息）
git clone 链接地址

#查看制定文件状态
git status [文件名]

#查看所有文件状态
git status

#添加所有文件到暂存区
git add . 

#提交暂存区中的内容到本地仓库 -m:提交的信息
git commit -m "信息"

```


## 参考资料
[B站视频链接](https://www.bilibili.com/video/BV1V54y1n7Wn/?share_source=copy_web&vd_source=de3781bf44c9af553019ed79ccd92886)

[博客文字教程](https://blog.csdn.net/weixin_48152652/article/details/124258293?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169753029816800197051283%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169753029816800197051283&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-124258293-null-null.142^v96^pc_search_result_base4&utm_term=git%E6%95%99%E7%A8%8B&spm=1018.2226.3001.4187)
