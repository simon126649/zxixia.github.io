---
layout: post
title:  "Windows中安装Jekyll"
categories: Web
tags: 教程 Jekyll
author: 西夏
description: 介绍如何在Windows环境下安装Jekyll的详细步骤。
---

### 1，安装Ruby
从这个[**链接**][ruby-download-link]点击下载**Ruby**，然后安装。

--- 
### 2，安装RubyGems
然后再从这个[**链接**][gems-download-link]下载**RubyGems**。
然后解压，在目录中敲如下命令，使用ruby进行安装：

`ruby setup.rb`

![ruby install gems][ruby-install-gems]

--- 
### 3，安装Jekyll
最后使用RubyGems安装jekyll。

`gem install jekyll`

![ruby install jekyll][ruby-install-jekyll]

[ruby-install-gems]:/images/post/2017-09-08-install-jekyll-to-windows/ruby-install-gems.png  "ruby install gems"
[ruby-install-jekyll]:/images/post/2017-09-08-install-jekyll-to-windows/ruby-install-jekyll.png  "ruby install jekyll"

[ruby-download-link]: https://rubyinstaller.org/downloads/
[gems-download-link]: https://rubygems.org/pages/download