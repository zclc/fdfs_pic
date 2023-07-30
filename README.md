# fdfs_pic
## 项目介绍

基于Fastdfs的图床存储服务器，实现了用户注册，用户登录，图片上传，  图片下载，图片分享功能
服务端采用nginx作为反向代理服务器，使用C语言，mysql，redis编写上述功能的fastcgi程序，采用docker容器部署
客户端使用qt编写，实现了注册，登录，文件浏览，上传，下载，分享功能
关键特性：

* 秒传
* 后端模块独立
* 链接分享
* docker部署

## 项目演示

### 登录注册：

![](http://47.100.86.209:8080/group1/M00/00/00/rBIAAmTGCy-AKcxhANImGXZTM3Q666.gif)

### 上传文件：

![](http://47.100.86.209:8080/group1/M00/00/00/rBIAAmTGCCmANfaxAMAnc8GDjNg022.gif)

### 下载文件：

![](http://47.100.86.209:8080/group1/M00/00/00/rBIAAmTGCG-AFtp7AXbrKfKkGJI121.gif)

* 分享图片

![](http://47.100.86.209:8080/group1/M00/00/00/rBIAAmTGCwWAdjyGBQeO9XK2YnM283.gif)



## 服务端结构

![](http://47.100.86.209:8080/group1/M00/00/00/rBIAAmTGG6GAWGsqAATBp-uHCJQ177.svg)



* Nginx用于web服务器，同时将作为fastCGI代理服务器，将fastCGI请求转发给FastCGI进程管理器，还会将FastCGI处理结果转发给客户端；

* MySQL用于存储用户信息，文件信息和FastDFS文件fileid；

* Redis作用：存储token, 登录名对应的token值，并设置过期时间。

