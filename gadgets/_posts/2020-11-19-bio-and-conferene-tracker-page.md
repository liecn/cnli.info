---
layout: post
title: 建立自己的Bio和Conference Tracker网页
description: 需要尝试着把自己推销出去，同时为开源做些贡献。
permalink: /bio-and-conference-tracker-page/
categories: [gaia, gadgets]
tags: [Bio, Conference Tracker, Web Development, Template]
date: 2020-03-31 22:25:30
---

# 　

## 开端

“万事开头难” 真是很真切的击中我的心灵了。我过去有过很多计划，也对新鲜事物抱有极大的热情，它却往往会被无法短期变现的收益与巨大期望的落差所消磨殆尽。我想如果能有记录的习惯，对我这个“目的性强“的人或许会有望梅止渴的奇效吧。如若这样，只盼不会在被人指责”不作为“了吧。

本文的重点在于，基于已有的开源代码，完成自己的Bio的设计与搭建，同时尝试维护一个本领域内top-tier会议的时间节点网页，用于对目标会议进行计时与追踪。

注：本文内容于2020年11月19日测试并进入维护，[代码完全开源](https://github.com/liecn/cnli.me)，欢迎使用或send your pull request。

## Bio Page

我个人偏向较整洁简约的网页风格，希望能在单页面内容的约束下向浏览者快速的推销自己。有先后尝试过wordpress，jekyll的模版，基于vue脚手架从0开始，但功能的冗余性以及界面的不适感让我对内容的维护丧失了基本动力。

这次的网页模版选择了师兄 [Longfei Shangguan](https://shanggdlk.github.io/)，单页面html，没有多余的脚手架及库的引入，但整体的简洁却让我倍感舒适。

我其实并没有做太多的修改，只是对相关尺寸，配色，链接进行定制化。因为是学术主页，内容上还是力求做到严肃认真。唯一俏皮的一点就是引入一些粉色的元素吧。

### 小目标：
  - 导航栏的配置。（就目前的学术记录，似乎有些操之过急，Lol。）
  - 图片加载的优化，需要自己的image CDN。
  - 提供更多的内容吧，hhh。

👉  请接受我的推销：[Chenning Li](https://cnli.me/)

## Conference Tracker Page

想维护一个top-tier conference的追踪界面的初衷有二：
- [Cheshu师兄](https://cswu.me/index.html#bio) 的 [conference link](http://ct.cswu.me/) 对我的科研起步有很大的主力，因为，每天看看那个dream conference的时间节点都是很振奋人心的事情呀！
- 我想尝试对开源和本领域的学术研究做一些贡献。通过调研发现关于AI的会议tracker多如牛毛，但network-related的page却凤毛菱角。 

有了初衷，接下来就是设计。

当前维护的会议仅限于自己的科研领域，通过对 [ACM SIGS](https://dl.acm.org/sigs) 的分类条目进行筛选，确定了SIGMOBILE, SIGAI, SIGCHI, SIGCOMM,SIGKDD, SIGSAC等主题。其次关于内容，我作为使用者，其实对会议的时间节点更为关注，包括abstract及full paper的截止日期，这里期待有三个功能，一是能够给出倒计时，二是能够转为使用者所在时区的时间，三是支持日历倒入等功能。然后就是找相应的轮子了，哈哈！其实主要是两个挑战，一是网页的模版设计，还是要秉持简约整洁的风格，二是会议信息的导入与更新。基于用户体验，我最终选择了 [abhshkdz](https://aideadlin.es/?sub=ML,CV,NLP,RO,SP,DM) 的模版，基本符合我心目的要求。（由github 🌟🌟 数目及贡献者列表不难看出AI真是当红辣子鸡）。最后就是定制化了。

### 定制化：
  - 对会议分支进行了细化和色彩修饰，并重新布局。
  - 考虑到本领域会议的特点，加入一栏用于显示abstract date的倒计时。
  - 移除无用的页面，使之成为一个简约的单页面应用。
  - 移除url的参数现实，使起更加整齐，便于分享。

关于会议信息的导入与维护，目前看出去人为导入并无很好的资源可供使用，希望之后改进。

👉  请接受我的推销：[CS Conference Tracker](https://cnli.me/conference/)

## End

以上便是我的第一篇Blog了，其实看样子更像是在做分享。我个人只希望这小小的一步能作为我博士生涯的开篇。未来日子还很长，学会独处和享受生活算是我对自己撇开学术的小小希冀吧！

最后放上我近期立下的flag以作督促吧！希望不倒。
  - 日语的学习还是要捡起来的，日本的花火大会还是在日程上的！
  - 刷视频和股票的时间倒不如多用来读读书啥的，书单列了那么长也该割割草了。
  - 科研上要软硬兼施，齐头并进！ 
