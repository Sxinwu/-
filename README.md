# README

## 项目说明

这个项目是在 2022.01.19 开发并部署完毕的一个网站后台，目前（2022.01.19）是使用 ip 访问的。由于牵扯技术十分简单，十分适合初学 SpringBoot 的初学者学习

## 功能说明

概述：本项目所实现的功能十分简单，是一个留言板，前端发起留言请求，后端接收到请求后，将留言内容保存至mysql数据库并将留言内容组合成句子发送至指定的邮箱

具体细节：

* 前端的表单为三个字段，分别是

  * 我们对您的称呼（必填）
  * 您的联系方式（邮箱或者电话，必填）
  * 您的需求（可选）

  如果两个必填项是空或者全为空格，应弹出弹窗进行相应的提示。

  所填写的信息由 Ajax 以 Post 提交方式提交到相应的 Controller 中

* 后端的 Controller 在接收到请求后，需要获取请求头的 ip 地址，以及留言时间，识别前端提交的信息中是否有需求信息，如果没有，将其填充为“未提供”，然后将信息插入到 MySQL 数据库中，接着将信息（前端的三个字段 + 留言者的ip + 留言时间）发送至指定的邮箱。

* 通过 Ajax 对象的状态信息，判断后端业务是否全部完成，如果没有，那么就显示类似“留言成功”的弹窗，否则显示“留言失败”

* 数据库中的留言不在前端展示，不对留言信息的长度进行约束（这个统计字符数就行了，很简单）

## 技术栈 

* 为了使得网站为响应式，自动适配屏幕，使用了bootstrap，这是一个为响应式而生的框架，自带 jQuery
* 前端提交使用了 Ajax，并针对 IE 做了特殊处理，避免 IE 浏览器无法产生 Ajax 对象的错误
* 后端主要使用了 SpringBoot，版本为 2.6.2，为当前的最新稳定版本
* 数据库使用的是 本人自己的阿里云服务器建（非宝塔安装）的 MySQL8.0.26 数据库，为本人在给服务器安装 MySQL 时的最新版本，项目中使用的 MySQL 驱动版本也为 8.0.26 使用了 MyBatis 框架进行数据库的增删改查
* 项目中使用了 lombok 插件

##  获取详细开发文档 

该文档永久链接：https://blog.qiql.net/SpringBootTorial(1).html

前端由 ==@==[shenxinwu.com](https://shenxinwu.com) 开发，后端由 ==@==[qiql.net](https://qiql.net)  开发

欢迎访问本人的个人网站：[qiql.net](https://qiql.net)，本人平时写的一些博客都会放在：[blog.qiql.net](https://blog.qiql.net) 上
