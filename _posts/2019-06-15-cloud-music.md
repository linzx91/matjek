---
layout: post
title: "在 Jekyll 博客添加网易云音乐插件"
date: 2019-06-15 21:05:00
categories: Jekyll插件
tags: 网易云音乐 插件 音乐插件 Jekyll插件 Jekyll博客
comments: 1
---

> 利用网易云音乐生成的 iframe 外链，插入到 Jekyll 博客文章中，只需要几行代码就能够实现。

<!--more-->

首先需要在 `_include` 目录下创建一个 `cloud-music.html` 文件，然后在文件中添加以下代码：

{% highlight html linenos%}
{% raw %}
<iframe frameborder="no" border="0" marginwidth="" marginheight="0" width="100%" height="86"
src="//music.163.com/outchain/player?type=2&id={{ page.music-id }}&auto=1&height=66">
</iframe>
{% endraw %}
{% endhighlight %}

将整个 `cloud-music.html` 嵌入 `post.html` 具体位置可以根据个人，具体代码如下：

{% highlight html linenos%}
{% raw %}
<!-- cloud music -->
{% if page.music-id %}
{% include cloud-music.html %}
{% endif %}
{% endraw %}
{% endhighlight %}

然后在需要添加音乐的博客文章开头的配置项添加`music-id: `  // 网易云音乐的歌曲id

**效果就是下面这样：**

<iframe frameborder="no" border="0" marginwidth="" marginheight="0" width="100%" height="86"
        src="//music.163.com/outchain/player?type=2&id=1355089626&auto=1&height=66">
</iframe>

<br>

> 还有另外一种方法就是直接在 `_layouts/post.html` 文件中添加以下代码：

{% highlight html linenos%}
{% raw %}
{% if page.music-id %}
<iframe frameborder="no" border="0" marginwidth="" marginheight="0" width="100%" height="86"
src="//music.163.com/outchain/player?type=2&id={{ page.music-id }}&auto=1&height=66">
</iframe>
{% endif %}
{% endraw %}
{% endhighlight %}

同样在需要添加音乐的博客文章开头的配置项添加`music-id: `  // 网易云音乐的歌曲id
