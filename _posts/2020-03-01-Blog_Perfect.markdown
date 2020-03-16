---
title: 搭建个人博客历程
tags: [杂项note]
background_music: <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=100% height=86 src="//music.163.com/outchain/player?type=2&id=1424523772&auto=1&height=66"></iframe> 
date: 2020-03-01
---

***

好久之前就看到别人搭建的这种博客(~~羡慕，想拥有~~) ，然后刚刚好大一寒假因为疫情变得超级长，所以就看着网上的教程开始了折腾

开发过程得益于谷歌搜索  
[(等有无聊的时间就更新搭建框架的详细教程)](https://fengwei2002.github.io/posts/Project_Description)

各种功能前人都有完整教程，跟着做就行了  
这里列出我的所有参考资料，感谢

> 参考资料

[Jekyll + Github Pages博客搭建入门](https://www.jianshu.com/p/9f198d5779e6)   
[Jekyll 博客 Next主题超深度配置](https://blog.csdn.net/ds19991999/article/details/81516568)   
[应用软件: Jekyll配置](https://www.jianshu.com/p/bb184f61c9ae)   

[优化Jekyll网页访问速度](https://zjiajun.github.io/articles/2015-01/optimization-of-jekyll-blog-access-slow-problem)

基本构建完成后就可以开始添加一些自己想要的功能，想添加什么功能就用谷歌搜，应有尽有

***

> 2020-01-20-----

# 🥇**已完成的功能模块**🥇

## 域名

* [x] **绑定域名**  

> 有需要时续费即可

https://fearlessroy.net/2018/01/29/binddomain/

[https://cloud.tencent.com/developer/article/1421879](https://cloud.tencent.com/developer/article/1421879)

使用腾讯云购买域名

## Live2D

* [x] **加入 Live2D 看板娘**

> 这里给出我的参考链接，之后会自定义一个属于自己的模板
> [网页添加 Live2D 看板娘。](https://www.fghrsh.net/post/123.html)
> [](https://imjad.cn/archives/lab/add-dynamic-poster-girl-with-live2d-to-your-blog-02/)
> 第二个链接的博客弄的非常好看

* [ ] DIY 看板娘

## 文本渲染效果

* [x] **$katex$ 行间公式渲染**

``` html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/katex/dist/katex.min.css" />
<script src="//cdn.jsdelivr.net/npm/katex/dist/katex.min.js" defer="defer"></script>
<script src="//cdn.jsdelivr.net/npm/katex/dist/contrib/auto-render.min.js" defer="defer" onload='renderMathInElement(document.body, { delimiters: [{ left: "$", right: "$", display: false }] })'></script>
```

``` html
<script src="//cdn.jsdelivr.net/npm/katex/dist/contrib/mathtex-script-type.min.js" defer="defer"></script>
```

* [x] **mermaid 流程图**

``` html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.css" />
<script src="//cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js" defer="defer" onload='
    for(let x=document.getElementsByClassName("language-mermaid"), i=0;i<x.length;i++)
    {
      x[i].classList.add("mermaid");
      x[i].classList.remove("language-mermaid");
    }'></script>
```

* [x] **网易云模块**

``` html
 网易云官方接口： 大歌单类型插入
 <iframe frameborder="0" border="1" marginwidth="0" marginheight="0" width="100%" height="450" src="//music.163.com/outchain/player?type=2&amp;id=553795744&amp;auto=1&amp;height=80">
 </iframe>
 标题类型插入
 <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=100% height=86 src="//music.163.com/outchain/player?type=2&id=(------)&auto=1&height=66"></iframe>
 id从网易云网址即可获得
```

> auto：0/1 1表示打开网页的时候自动播放。0表示打开网页的时候不自动播放；

* [x] **黑色代码块渲染代码块，关闭默认渲染效果**

> 2020-03-04 background_music：要变好看~；要变好看~

 在[https://github.com/PrismJS/prism/tree/master/themes](https://github.com/PrismJS/prism/tree/master/themes) 内查看可用主题，或者也可以搜一些第三方主题

* [x] **字体样式：**
* 采用 Source Code Pro 加等宽字体构建

``` css
.sidebar {
  font-family: Menlo, Monaco, "Source Code Pro", Microsoft JhengHei, monospace;
}
```

* [x] **雾化**

> 防止背景影响阅读体验

``` css
.container {
  background-color: rgba(255, 255, 255, 0.7);
  box-shadow: 0 0 1rem 1rem rgba(255, 255, 255, 0.7);
  text-shadow: 1px 1px 1px rgba(255, 255, 255, 0.021);
  min-height: 3vh;
}
```

## 评论

上次见到别人自己写了一个评论 t q l

* [x] **评论系统gitalk**

2020-03-04

> 原理：使用GitHub账户即可直接进行评论储存在 comment 里的 issue 中

> 但是不能 DIY 样式并且会因为汉字转换后的 url 有时太长所以崩掉

> 缩短文件名为50字符以下后 gitalk 就能愉快的使用了用了

> 启用Facebook沉浸式评论

配置详细步骤请参考以下博文：

[https://aerolith.ink/2018/08/25/Gitalk/](https://aerolith.ink/2018/08/25/Gitalk/)

[https://draveness.me/git-comments-initialize](https://draveness.me/git-comments-initialize)

## 美化

* [x] **彩色滚动条**

> 花里胡哨+1

``` css
::-webkit-scrollbar {
  width: 3px;
  height: 7px;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
}
```

* [x] **动画淡入淡出效果**

> 花里胡哨+2

``` css
.masthead,
.content,
.sidebar-toggle,
.pio-container {
  animation: animationAppear 2s;
}

@keyframes animationAppear {
  0% {
    opacity: 0;
  }

  33% {
    opacity: 0;
  }

  100% {}
}
```

* [x] 爱心点击渐变效果

2020-03-02

> 花里胡哨+3

在 `</body>` 结束前进行一次 $js$ 引用就ok了

* [x] 鼠标指针点击烟花动画

> 花里胡哨+4

2020-03-10 完成

> 每次鼠标右键点击出现击碎砖块的烟花效果

***

# 💎 未完成的功能模块

> 需求与日俱增；虽然是一个慢慢经营的个人空间；但也欢迎你和我一起来完成剩余功能的构建

* [ ] gitbook目录样式

我想弄成 gitbook 那种目录不隐藏；然后随着文章滚动同时进行的架构

以后肯定会重构一遍；目前样式手机端目录效果应该保留

而电脑左右都剩下一大块；而看板娘只需要空白布局的四分之一；所以左面的中间部分应该放一个动态目录；而不是什么都没有

就是进入博文后应该变成干干净净且方便的样式 `eg:gitbook` 

* [ ] 翻页功能, 按照时间线查询前后文章翻页

> 上一篇，下一篇那种 ，博文多了后还可以按照标题**在文章末尾推荐猜你喜欢**

* [ ] 想弄一个顶部显示实时播报的进度条

> 这样：
>  

![46AE5778012E9A0825C0CA51EEB3A56A.jpg](https://raw.githubusercontent.com/fengwei2002/Pictures_01/master/Pictures_0146AE5778012E9A0825C0CA51EEB3A56A.jpg)

* [ ] 赞赏模块(没用)

> 写博客又不是为了得到 ￥ ，但应该尝试模块化这个功能，失陷后关闭即可

* [ ] 首页展示背景图片；而当点开博文时，图片透明度极低或 0

> 比下面这个透明度再高一些

![36D86354C88A093D009CC82EC44D50E7.jpg](https://raw.githubusercontent.com/fengwei2002/Pictures_01/master/Pictures_0136D86354C88A093D009CC82EC44D50E7.jpg)

* [ ] 完成一个自定义的live2D模块

* [ ] 点赞系统的搭建

> [看看人家](https://priesttomb.github.io/)

* [ ] 鼠标指针预览动画

> 听说JavaScript 可以实现 (这个功能很好看)
> 就是比如挪到一篇博文上；出现一个博文内容的小方框；当挪到一张图片上时；出现图片预览方框；当挪到一个选项时；出现选项的详情

* [ ] 添加一个博文置顶按钮
* [ ] 添加一个分享按钮；与置顶按钮放在上下，一人一个小方格
* [ ] 图片下面显示注释信息且能够被点开放大
* [ ] 加速博客国内访问速度（这个最$\dots$)

## 结尾

时间弹指一挥间  且行且珍惜

