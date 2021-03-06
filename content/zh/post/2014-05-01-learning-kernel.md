+++
title = "Learning Kernel"
date = "2014-05-01T06:14:08+08:00"
slug = "learning-kernel"

+++


我是从大二开始使用linux系统的, 当时除了玩单片机之外, 所有工作完全在linux完成, 克服了种种"困难". 不过现在看来自己除了佩服自己当时的热情之外, 就只觉得自己太幼稚了. "在正确的时间做正确的事情, 用正确的工具做正确的事情." 就像以前一直很偏爱C语言一样, 一定要写成内核模块, 内核线程... 现在自己变得更加聪明了.

我大学期间一直没有机会碰linux内核, 只有在大三下的时候, 在实验室玩ARM开发板, 才知道, 原来linux内核做了这么多的工作, 一个hello world能够轻松的运行起来, 背后有多少的东西在默默无闻的工作着.

毕业后我按照自己的规划找了一份嵌入式软件开发的工作. 公司也还算给力, 给了我足够的时间来学习. 我当时是从驱动入手的, 主要看了一本书和一个英文文档, 分别是LDD3和LKMPG. 这本书我前段时间又看了一遍, 觉得这个不适合一个新手看, 难怪我当初看的那么累, 原因有是作者在书内容里无缝地介绍了软件架构, 代码复用等等对于新手来说高级的东西, 这些应该属于软件工程的内容, 这样当然有好处, 但是给人感觉就是复杂, 相比之下国内的书会简单直接很多. 另外LDD3是基于2.6内核的API写的驱动, 已经有大牛移植到linux3.x上面了.

其实, 内核代码发展很快, 差几个版本基本就面目全非了, 所以, 要多看, 多思考, 有整体把握. 这样, 过段时间拿到最新的代码了, 自己也有能力跟踪进去.

最近, 在linux社区上面看了几篇有趣的东西, 在HN上貌似也火了一下, 所以, 分享出来给大家玩下.

## Eudyptula
模仿Matasano Crypto Challenge(集中48小时的练习, 培训参与者密码系统如何建立以及如何被攻击), 面向linux内核的一系列编程练习, 任务难度逐渐增加. 一切是从给little@eudyptula-challenge.org发一封邮件说你要加入开始的. 由于实际的内核开发就是通过邮件列表沟通的, 所以, 必须要熟悉邮件工具是必备技能.

PS: 由于我发了邮件他还没回我, 呵呵, 后面等做了几个任务之后再跟大家分享一下.

## Kernel 101
这篇文章最近在HN上比较火, 教你从0开始写一个kernel, 当然功能仅仅是打印一行信息而已. 对于新手来说还是比较好的学习材料. 源码就2个文件, 一段汇编主要功能就是跳转到C程序的kmain函数; 一段C代码, 将显存内容清空并赋值为一段字符串.

其中几个关键知识点记录一下:
1. x86的CPU启动后从地址[0xFFFFFFF0]处开始执行, 这个是设计CPU时写死的. 从芯片手册上可以查到. 下面提到的一些地址都是芯片手册中规定统一的, 所以x86架构才能够通用, 各种OS都能安装, 不需要繁琐的移植工作.
2. 启动流程: 上电 -> CPU[0xFFFFFFF0] -> 跳转到内存中BIOS代码 -> 根据BIOS配置将物理设备第一个扇区的代码copy到物理内存的[0x7c00]位置(即boot loader的代码) -> bootloader将内核代码加载到物理内存[0x100000](x86 CPU宏内核代码起始地址, 也就是后面我们编写的汇编程序的链接地址).
3. 汇编代码中使用了一些nasm的伪指令, 所以, um, 看注释就好.
4. 通常的内核开发还需要提供一个根文件系统文件的, 这个简单例子是不包含文件系统的.
5. grub2下添加引导项的方法, 成败在于此, 需要注意你的/boot分区是否是一个独立分区, 如果不是独立分区那么ok, 安装作者的文章搞起; 如果你像我一样安装系统时候将/boot独立一个256M空间的分区, 那么要内核文件位置使用相对/boot相对地址. 另外注意, 要使用msdos2, 否则会失败.

```
$sudo vim /boot/grub/grub.conf

//在文件中其他引导项下面添加如下
menuentry 'Akagi201 Lovely Kernel' {
    set root='hd0,msdos2'
    multiboot /kernel-7001 ro
}
```

## What my new-born kernel says
um, 我改了一下颜色, 跟字符内容, 哈哈, 没啥技术含量啦!

![akgrub](http://akagi201.qiniudn.com/akgrub.png)

![akkernel](http://akagi201.qiniudn.com/akkernel.png)

## links
* The Linux Kernel Module Programming Guide: <http://tldp.org/LDP/lkmpg/2.6/html/> 看完这个你就能让内核输出hello world啦.
* LDD3-examples-3.x: <https://github.com/duxing2007/ldd3-examples-3.x> 你应该会注意到不同的branch对应不同的内核版本, 很赞吧!
* kernel 101 on HN: <https://news.ycombinator.com/item?id=7588205> 有人还做了FUSE版本, 作者也要出ARM版本了, 可以关注下, 上面作者有更多的细节解释.
