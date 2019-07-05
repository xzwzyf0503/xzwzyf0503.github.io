---
layout: post
title: 'Hello Github Pages，Goodbye CSDN'
subtitle: 'github jekyll 博客搭建'
date: 2017-09-16
categories: 技术
tags: githubPages
---

## 告别CSDN
很久之前看到过别人利用github pages建的自己的博客，怎么形容呢，好多不错的都是自己写的样式，有设计感又逻辑合理，部分酷炫的也非常有意思......但是眼馋归眼馋，可我只是个半路出家非科班的小小Android程序媛，前端基础不是渣，简直是没有基础...羡慕完毕就灰溜溜的闪了。

但是前几天，我偶尔用来记录问题的CSDN Blog 居然给了我一个这样的噩耗：
![csdn blog close](/assets/img/201709/csdn_close.png)
你告诉我，我做了什么！我说脏话了么，打广告了么？是，我的部分文章是转载了一些其他人的劳动果实，可是每一个都是注明出处的！无缘无故的，就给我关了......是不是有点任性了呀！

算了，我们互相抛弃吧，在这个看颜值的时代里，我也已经忍你那个丑丑的样子很久了。这个事情让我知道，一个自己能掌控的博客还是很重要的，于是我毫不犹豫得投入了Github Page的怀抱。话说为啥选他：
* 免费--工资很不可观的我，养自己就很累了，要钱的免谈
* 简单方便--搭建和写博客的语法都比较简单，对我这种前端白痴来说，易操作也很重要啊 
* 可控--所有的内容都存在git仓库，不论样式内容还是迁移都是你说了算

## 搭建
首先估计再渣的小猴子肯定都有一个github账号，登陆你的github，点击那颗绿绿的小按钮 _New repository_ 新建一个仓库，以后你的博客就托管在这里面了呢。
![create repository](/assets/img/201709/repository_create.png)
最主要的时候填入Repository name，每个这个是必须按规定来填的，yourname.github.io ，每个账号只可以建一个Github Page 的仓库，故意填错是啥效果我还没试过......

Description描述你随意填，接下来选Public就好了，Private要票票的，反正我不是土豪。其他的随意啦，这样就可以**Create repository**了。

创建完仓库，你就可以在自己仓库列表来看到它了，这个时候，其实通过仓库中的setting下的GitHub Pages中选择一个主题的页面生成器，就可以开始写你的博客了。
![select theme](/assets/img/201709/github_page_theme.png)
我想应该基本没有人满足于这个页面生成器吧，不过现在先试试我们的站点能不能访问，首先看下你的仓库里是否有index.html文件，这个是默认的导航页，不管是模板里自带的还是你自己写的，只有仓库存在这个页面，我们才能通过https://yourname.github.io，显示的内容就是index.html的内容。

只要人品不是很差，一般都能成功访问，而我就是那个人品差的，访问后显示404...... ⊙﹏⊙......看一下邮件，有问题github会给你当初注册的邮箱发送邮件的，每个人的问题可能不太一样，按他的提示把问题解决了，就可以访问了。

刚刚说了，基本大家都不会满足与一个生成器主题，而我技术有限，关键还懒.....就找了现成的Jekyll主题的博客模板（jekyll是一个简单的静态博客网站生成器）。

首先jekyll需要需要ruby语言支持，mac是自带的，没有的话也可以装，我的在安装jekyll的时候提示和版本太旧了更新了最新的。ruby的安装命令入下：
```css
	brew install ruby
```
Gem是Ruby的第三方插件管理器，更新Gem
```css
	sudo gem install --system
```
很多人说要跟换源列表，可能会被墙，但是我没有换，就用原来的也可以安装，就是比较慢......
```css
	# 查看源列表
	gem sources -l
	# 将源移除
	gem sources --remove https://rubygems.org/
	# 添加国内源
	gem sources --add https://gems.ruby-china.org/
	# 缓存
	gem sources -u 
```
然后安装jekyll 
```css
	sudo gem install jekyll
```
上面这些命令如果像我一样傻傻不换来源慢慢下的，可以再命令后面加上 -V，会打印过程，不然半天窗口都没变化也不知道它在不在干活。

安装bundler(捆绑器的软件包管理器)，其实我并不懂这时候什么鬼，看了下解释还是有点懵，管理多版本gem？反正就是要依赖。
```css
	sudo gem install bundler
```
还有些不装暂时也没影响的这边先跳过，安装完必须的工具后，要选一个jekyll主题，这个纯粹看个人喜好了呀，github上还有star几千的主题，但我还是选了个star少的...喜好是没有道理可言的~

[H2Ourl]:https://github.com/kaeyleo/jekyll-theme-H2O
这个主题是[H2O][H2Ourl],感谢它的作者 **kaeyleo**

首先把自己的博客仓库clone 到本地你自己选的目录下，比如我新建了个目录叫GithubPage，到这个目录下，执行
```css
	clone https://github.com/yourname/yourname.github.io
```
下面git的基本操作就不贴代码细说了，选择你对的上眼的主题，因为要放到自己的仓库里，而且后期可能想要改改，所以直接下载了。
![select theme](/assets/img/201709/download_theme.png)
把下载后解压的内容放到你的仓库的目录下，我们要在本地调试需要生产博客，开启本地预览，命令如下：
```css
	#生成博客，默认生成在_site目录下，在配置文件中可自定义更改
	jekyll build
	#启动jekyll本地预览
	jekyll server
```
在浏览器中输入 <http://localhost:4000>(或者<http://127.0.0.1:4000>) 就能访问了。

现在，我们可以开始改改改了，我的水平也只能改改字体、颜色，微调个样式，加个留言啥的......改结构分分钟毁掉一个好主题，不会......

主题的需要修改的内容基本上在config文件中，当然像index.html中的主页你肯定是要改的，demo中自带的文章最要删掉，不过前期可以拿来参考。

主要的配置项看主题的github主页都有说明，添加文章用的markdown语法搜搜，上手还是比较快的，再来就是看主题中的代码，找不到的设置就需要你自己改主题了

巴拉巴拉，修改过程还是看大家的需求和喜好，等改的差不多了，把仓库中的修改都提交。

OK，你的个人博客就建好了！通过https://yourname.gitbug.io/看看吧~




