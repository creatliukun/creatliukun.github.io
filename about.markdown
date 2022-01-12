---
layout: page
title: 我的
permalink: /about/
---

```bash
4.1 获取AppID和AppKey
Valine评论系统是放在LeanCloud上的，因此首先需要去注册一个LeanCloud账号。
注册地址：https://www.leancloud.cn/
进入控制台后点击左下角创建应用，名字可以随便起，选择开发版：

应用创建好以后，进入刚刚创建的应用，选择左下角的设置>应用Keys，然后就能看到你的AppID和AppKey了（复制保存一下，一会好用）：

为了数据安全，配置一下Web安全域名：

4.2 获取HTML片段
访问Valine官网：https://valine.js.org/
复制HTML片段，修改初始化对象中的appId和appKey的值为上面刚刚获取到的值即可(其他可以默认)
4.3 引入HTML片段
我是新建了一个comment.html页面，然后在需要加评论的地方引入这个页面：
我需要在每篇博客文章的详情页最后添加评论功能，所以在_layouts/post.html页面引入评论页面内容：

5. 访问量统计
5.1 注册百度统计账号
访问百度统计：https://tongji.baidu.com/，注册百度统计账号：
登录百度商业账号：
5.2 新增网站
新增网站（管理->网站列表->新增网站）：

5.3 代码获取
点击“获取代码”：
5.4 引入代码
把代码复制到header.html头模板页面中即可。
我放的位置如图所示
提交代码后，点击“代码检测”，检查代码是否安装正确：
```
