---
layout: post
title:  "Github Pages创建个人网站以及域名绑定"
categories: Web
tags: 教程 Jekyll GithubPages
author: 西夏
description: 介绍如何使用Github Pages创建一个简单的个人网站，并绑定自定义域名的全过程。
---

### 1，创建Github项目
按照下面格式创建一个公开的Github项目：

**`your_github_username.github.io`**

假设你的Github的用户名是**tanglaoya**，则你需要创建一个名为**tanglaoya.github.io**的公开项目。

---
---
### 2，创建首页
复制并保存下面的代码到index.html文件中：
{% highlight html %}
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>Hello world!</title>
	</head>
	<body>
	<p>Hello World!</p>
	</body>
</html>
{% endhighlight %}

---

然后将该文件push到你刚才创建的**`your_github_username.github.io`**项目中去，此时你的项目目录如下：
{% highlight shell %}
root
 |-index.html         # 网站首页
{% endhighlight %}

---
浏览器访问**`https://your_github_username.github.io/`**，如看到Hello World!表明Github Pages创建成功。


---
---
### 3，绑定自定义域名
#### A，Github的设置
进入你的**`your_github_username.github.io`**项目的**Settings**的**GitHub Pages**选项卡。

---
![settings page][settings-page]

在**Custom domain**那里输入你的域名，并保存。

---

此时，你的项目的目录结构如下：
{% highlight shell %}
root
 |-index.html         # 网站首页
 |-CNAME              # Github创建的，只有一行你刚才输入的域名的文件
{% endhighlight %}
多出来的**CNAME**是Github自动创建的，该文件只有一行，就是你刚才输入的域名。

---

#### B，添加你的域名的解析
更改你的域名解析设置，添加如下的三组记录：
![add custom domain][add-custom-domain]

然后等你的解析生效以后，即可直接通过**`https://your_domain.com/`**访问你的个人网站了！

---
---
### 参考资料：

1，[一步步在GitHub上创建博客主页-最新版][Wave-at-csdn]






[settings-page]:/images/post/2017-09-11-start-github-pages/settings-page.png "settings page"
[add-custom-domain]:/images/post/2017-09-11-start-github-pages/add-custom-domain.png "add custom domain"

[Wave-at-csdn]: http://blog.csdn.net/wave_1102/article/details/41548951