---
layout: post
title: 为Blog添加背景音乐
description: 没有音乐不爽，而且我很恶毒的隐藏了关闭音乐的标签。
category: coding
---

## 添加音乐其实很简单，但是找外链太恶心了


中了Yuna Ito的I'm here的毒了， 单曲循环中，折腾了一下午，终于找到了一个能用的外链放到了Blog的背景音乐中

***

添加背景音乐的代码其实很简单,需要注意的是embed在手机浏览器中是不支持的：

    <embed src="http://other.web.rh01.sycdn.kuwo.cn/resource/n1/57/87/2161892006.mp3" hidden="true" autostart="true" loop="true">

***

虽然一句代码很简单，但是神烦的是找到音乐的外链的过程，经过近两个小时的搜寻终于在贴吧找到了一个在酷我上扒外链的方法：

1. 链接前缀 http://player.kuwo.cn/webmusic/st/getNewMuiseByRid?rid=MUSIC_
2. 随便找一首歌 http://www.kuwo.cn/yinyue/1034671/
3. 把歌曲链接的数字贴到链接前缀后面 http://player.kuwo.cn/webmusic/st/getNewMuiseByRid?rid=MUSIC_1034671 用浏览器打开这个链接，会有一段服务器返回的代码
4. mp3dl是外链地址的前半部分，mp3path是外链地址的后半部分，将他们用/resource/连起来，前面再加上http://就是完整的外链地址啦

