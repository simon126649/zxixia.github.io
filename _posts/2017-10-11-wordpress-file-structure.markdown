---
layout: post
title:  "WordPress文件目录结构"
categories: Programmer
tags: WordPress
author: 西夏
description: WordPress学习笔记一，WordPress文件目录结构说明。
---

{% highlight shell %}
   root\
    |
    |-wp-admin\             # 后台管理需要的类和文件
    |
    |-wp-includes\          # WordPress强大的类库，及核心函数定义
    |  |
    |  |-class-*.php        # WordPress定义的类
    |  |-post-template.php  
    |  |  |-the_ID()
    |  |  |-the_title()
    |  |           
    |  |-wp-db.php
    |  |  |-query()
    |  |  |-insert()
    |  |  |-update()
    |
    |-wp-content\            # 主题开发主要就是修改这个目录下的文件，其他文件不要动！
    |  |
    |  |-languages\          # 多语言包，使用Poedit编辑和创建语言包
    |  |-plugins\            # 插件安装目录
    |  |-themes\             # 主题安装目录
    |  |-uploads\            # 文件上传目录
    |  |-upgrade\
    |  |
    |  |-index.php       
    |
    |-index.php              # 核心索引文件，博客输出文件
    |-license.txt            # GPL许可证
    |-readme.html            # 安装说明
    |-wp-activate.php        # 用户注册激活
    |-wp-blog-header.php     # 加载WordPress环境和模板
    |-wp-comments-post.php   # 评论相关操作
    |-wp-config.php          # 链接MySQL数据库的配置文件，安装完WordPress后自动生成
    |-wp-config-sample.php   # WordPress官方给出的连接MySQL数据库的配置示例
    |-wp-cron.php            # 执行定时任务
    |-wp-links-opml.php      # 生成OPML格式的链接列表，通过WordPress的管理菜单添加
    |-wp-load.php            # 加载wp-config.php和设置公共变量，加载WordPress程序和类库
    |-wp-login.php           # 定义注册用户登陆界面
    |-wp-mail.php            # 邮件操作
    |-wp-settings.php        # WordPress运行前例行程序，检查安装是否成功，加载辅助函数，用户插件初始化等
    |-wp-signup.php          # 用户注册，WordPress多站点功能
    |-wp-trackback.php       # 处理trackback请求
    |-xmlrpc.php             # 远程发布功能
    |
{% endhighlight %}





<!-- 后面是文章参考资料 -->
<br/>
### 特别鸣谢：

1，[《跟黄聪学WordPress主题开发》][hc]

<!-- 文章插图和超链接 -->
[hc]: http://wphun.com/673
