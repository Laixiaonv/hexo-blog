---
title: npm
date: 2021-03-05 00:02:59
tags:
---

> npm是一个包管理工具

> 可以废弃

> 删除限制（不鼓励删除，可以废弃，因为你发的包可能已经被他人引用，如果删除，其他已引用包依赖的工程会出现问题）
+ 删除的版本24小时后方可重发!
+ 只有发布72小时之内的包可以删除!

> 区别
+ 废弃不会将包或版本从npm仓库删除，仍然可以继续下载安装，并在安装的时候会有警示
+ 删除会将包从npm彻底删除，无法被下载安装

### package
> 含有`含有package.json描述文件`并`发布到npm仓库`的文件或文件夹

+ Scope(作用域、范围)
  可作为包的命名空间
  @Scope/babal
  @Scope/fg-antd
  `为发布的包提供命名空间，防止与他人的包名冲突`
  
+ Accessibility(可访问性)

### module

> 主要在node环境被引用，可以require()方法加载
> 在`node_modules`中，可以`被Node.js的require()方法加载`的任何文件或文件夹

**必须是下列情况之一**
+ 必须包含package.json，且含有main 字段
+ 含有index.js的文件夹
+ js文件

**注意：**
+ module不一定是package（比如node内置模块），package一定是module
+ 含package.json文件的module一定是package

### 发布

+ 注册npm 账户
+ 全局安装nrm => 是npm仓库管理的软件，可用于npm仓库的快速切换
+ 项目官方建议规范
    + package.json（包的基本信息）
    + README.md（文档）
    + index.js （入口文件）
+ 发布 
    + unscoped包
    创建项目 => npm publish
    + scoped包
    创建项目 => npm publish => **加作用域** npm init --scope=@scoped -y

### 废弃
npm deprecate <pkg>[@<version>] <message>

🌰 npm deprecate yuyy-test-pkg@1.1.0 'test deprecate'
    
### 删除

npm unpublish <pkg> --force
