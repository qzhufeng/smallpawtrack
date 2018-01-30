---
title: github page + hexo
date: 2018-01-30 16:46:38
tags:
categories: 
---




# 一 hexo install 安装

也可以参考 [hexo官方中文文档](https://hexo.io/zh-cn/docs/)

## 1.1 node.js + npm 安装

node.js是javascript的一种运行环境，是对Google V8引擎进行的封装。是一个服务器端的javascript的解释器。
包含关系，nodejs中含有npm，比如说你安装好nodejs，你打开cmd输入npm -v会发现npm的版本号，说明npm已经安装好。

引用大神的总结:

其实npm是nodejs的包管理器（package manager）。我们在Node.js上开发时，会用到很多别人已经写好的javascript代码，如果每当我们需要别人的代码时，都根据名字搜索一下，下载源码，解压，再使用，会非常麻烦。于是就出现了包管理器npm。

大家把自己写好的源码上传到npm官网上，如果要用某个或某些个，直接通过npm安装就可以了，不用管那个源码在哪里。并且如果我们要使用模块A，而模块A又依赖模块B，模块B又依赖模块C和D，此时npm会根据依赖关系，把所有依赖的包都下载下来并且管理起来。试想如果这些工作全靠我们自己去完成会多么麻烦！

### 1.1.1 For Windows

在[node.js官网](https://nodejs.org/en/)下载[安装包](https://nodejs.org/dist/v8.9.4/node-v8.9.4-x64.msi)，安装后会包含nodejs和npm。

## 1.2 hexo-cli 安装

设置适用淘宝的镜像源，然后安装hexo-cli
```
npm config set registry https://registry.npm.taobao.org
npm install -g hexo-cli
```

## 1.3 git 安装

前往[git网站](https://git-scm.com/download/win)下载[git-for-windows](https://github.com/git-for-windows/git/releases/download/v2.16.1.windows.1/Git-2.16.1-64-bit.exe)安装即可。



# 二 github page

Github Pages免费的静态站点，其特点：免费托管、自带主题、支持自制页面等。

创建Github Pages比较简单，只要你有一个github账号在创建一个仓库就行了，但是这个仓库是有规则的，其格式必须为：**project-name.github.io**。然后根据提示一直下一步即可，非常简单。


2.1、autocrlf
```
#提交时转换为LF，检出时转换为CRLF
git config --global core.autocrlf true

#提交时转换为LF，检出时不转换
git config --global core.autocrlf input

#提交检出均不转换
git config --global core.autocrlf false
```
2.2、safecrlf
```
#拒绝提交包含混合换行符的文件
git config --global core.safecrlf true

#允许提交包含混合换行符的文件
git config --global core.safecrlf false

#提交包含混合换行符的文件时给出警告
git config --global core.safecrlf warn
```
2.3 filemode
```
git config --global core.filemode false
```

# 三 hexo创建项目

## 2.1 创建

```
hexo init project-name
cd project-name
npm install
```

## 2.2 hexo 其他命令参考[官网](https://hexo.io/zh-cn/docs/commands.html)


# 四 关联 hexo 和github page

## 4.1 配置git个人信息

```
git config --global user.name "xujun"
git config --global user.email "gdutxiaoxu@163.com"

ssh-keygen -t rsa -C "gdutxiaoxu@163.com"
```

## 4.2 安装一个git扩展：
```
npm install hexo-deployer-git --save
```

## 4.3 在_config.yml文件中配置
```
deploy:
  type: git
  repo: git@github.com:yourname/yourname.github.io.git
  branch: master
```

**==然后 ```hexo d``` 即可。==**


# 五 hexo 主题切换

## 5.1 切换next主题

github: https://github.com/iissnan/hexo-theme-next

参考github说明即可。



