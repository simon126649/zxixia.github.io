---
layout: post
title:  "Jekyll基本知识整理"
categories: Web
tags: 教程 Jekyll
author: 西夏
description: 本文总结了本博客开发过程中用到的Jekyll基本知识。
---

### 1，整体大观
**西夏情报站！**网站目录格式如下：
{% highlight shell %}
root
 |-_config.yml        # Jekyll 配置文件
 |-index.html         # 网站首页
 |-_layouts           # 布局文件夹
 |    |-default.html  # 最基础的布局,其余布局均在此基础上生成
 |    |-post.html     # 文章布局
 |    |-home.html     # 网站主页布局
 |-_includes          # 被引用的布局文件
 |    |-head.html     # html文件的基础头信息 
 |    |-header.html   # 网页顶部站点名称
 |    |-nav.html      # 顶部的导航条
 |    |-slide.html    # 右侧的侧边栏
 |    |-footer.html   # 底部的感谢信息
 |    |-foot.html     # html文件的基础后加载信息     
 |    |-tags.html     # 在文章下面显示tag信息的文件
 |-_data              # 存放Jekyll支持的数据文件夹
 |    |-links.yml     # 存放友情链接
 |-_posts             # 存放发表的文章
 |    |-*.markdown    # 以markdown格式书写的博文
 |-css                # css样式文件夹
 |    |-ie10-viewport-bug-workaround.css
 |    |-main.scss     # 自定义的css样式文件，引用_sass\下面的文件
 |-_sass              # 被应用的css样式文件
 |    |-blog.scss     # 网站的基本的css样式
 |    |-igorpro.scss  # rouge支持的代码高亮样式方案
 |    |-github.scss   # rouge支持的代码高亮样式方案
 |-bootstrap          # bootstrap文件夹
 |    |-css
 |    |-fonts
 |    |-js
 |-images             # 存放网站中的图片
 |-lib                # 引用的第三方js文件
 |    |-jquery-3.2.1.min.js
 |    |-ie10-viewport-bug-workaround.js
 |-site               # 存放网站二级目录文件夹
 |    |-about         # 二级目录，关于
 |    |   |-index.html
 |    |-category      # 二级目录，分类
 |    |   |-index.html
 |    |-tags          # 二级目录，标签
 |    |   |-index.html
 |-CNAME              # github pages域名跳转文件
{% endhighlight %}

***
***

### 2，Jekyll是如何布局的
本网站的首页布局文件**`index.html`**全部内容如下，可点击[链接][xixia-info-index]查看。
{% highlight shell %}
---
layout: home
nav: home
---
{% endhighlight %}

**说明**：开头包裹在两个**`---`**之间的是Jekyll的配置信息。这里通过**`layout`**属性指明当前文件的布局文件是**`home`**。
**`home`**指的就是**`_layouts`**目录下的**`home.html`**文件，该文件头部信息如下，完整代码可点击[链接][xixia-info-home-html]查看：
{% highlight shell %}
---
layout: default
---
{% endhighlight %}

**说明**：可知**`home.html`**使用的布局文件是**`default.html`**，完整代码点击[链接][xixia-info-default-html]查看。

![default.html page][default-html]

可看到，**`default.html`**文件中通过**`include`**命令引用了大量的代码片段。增强了代码的可读性和易于维护性，

**说明**：**`home.html`**页面的基本信息（头部，底部，导航等）由**`default.html`**统一提供。而**`home.html`**自身的页面内容，则填充到上图中由两个中括号括起来的**`content`**部分。

本篇博文使用的布局文件是**`post.html`**，可点击[链接][xixia-info-post-html]查看。

---
---
### 3，变量
#### a，site
定义在`_config.yml`中的量，如下：
{% highlight shell %}
title: 西夏情报站！
description: 西夏的个人网站，编程，历史，交通，文学，影视...
baseurl: "" # the subpath of your site, e.g. /blog
url: "" # the base hostname & protocol for your site, e.g. http://example.com
{% endhighlight %}
在其他文件中使用方式如下调用：

![how to use variable][how-to-use-variable]

#### b，page & post
定义在`_posts`文件夹下的文章中的量，比如这篇文章开头就定义了如下的许多量：
{% highlight shell %}
---
layout: post
title:  "Jekyll基本知识整理"
categories: Web
tags: 教程 Jekyll
author: 西夏
description: 本文总结了本博客开发过程中用到的Jekyll基本知识。
---
{% endhighlight %}

引用方法和前面的`site`变量一样，都是通过**`两对中括号扩起加.运算符`**引用。

>**注意**，`page`是在文章内部调用，`post`则是在文章外部调用。比如本网站首页和每篇博文内页都会在底部显示当前文章的标签信息。
>此时需要分清当前的调用对象，参考如下代码：

![how to use variable page & post][how-to-use-variable-page]

---
---
### 4，自定义数据
可在**`_data`**文件夹下，按照Jekyll支持的方式添加自定义数据。本网站的友情链接数据全部存储在**`\_data\links.yml`**文件中：
{% highlight shell %}
- url: "http://jiawa.net"
  title: "加瓦社区"

- url: "http://v3.bootcss.com/getting-started/"
  title: "Bootstrap 入门"
{% endhighlight %}

在**`\_includes\slide.html`**按如下方式调用显示友情链接：

![how to use custom datas][how-to-use-custom-datas]

---
---
### 参考资料：

1，[Jekyll Docs][jekyll-docs]






[how-to-use-variable]:/images/post/2017-09-09-summary-of-jekyll/how-to-use-variable.png "how to use variable"
[how-to-use-variable-page]:/images/post/2017-09-09-summary-of-jekyll/how-to-use-variable-page.png "how to use variable page & post"
[default-html]:/images/post/2017-09-09-summary-of-jekyll/default-html.png "default.html page"
[how-to-use-custom-datas]:/images/post/2017-09-09-summary-of-jekyll/how-to-use-custom-datas.png "how to use custom datas"

[jekyll-docs]: http://jekyllrb.com/docs/home/
[xixia-info-index]: https://github.com/zxixia/zxixia.github.io/blob/master/index.html
[xixia-info-home-html]: https://github.com/zxixia/zxixia.github.io/blob/master/_layouts/home.html
[xixia-info-default-html]: https://github.com/zxixia/zxixia.github.io/blob/master/_layouts/default.html
[xixia-info-post-html]: https://github.com/zxixia/zxixia.github.io/blob/master/_layouts/post.html