---
layout:     post
title:      使用开源的Inkscape来绘制矢量图
subtitle:   取代商业的Viso
date:       2020-04-13
author:     Haifeng
header-img: img/post-bg-BJJ.jpg
catalog: true
tags:
    - Inkscape Viso
---

<!--
这是海峰的第一篇博客帖子
-->

最近修改论文的时候，因为使用viso绘图时候打上去的mathtype的字符不是很美观，所以导师跟我推荐了[Inkscape](https://inkscape.org/)。

在viso中一般是利用mathtype公式编辑器来插入公式字符，但是因为viso是商业软件，所以这个需要授权或者破解。有一个解决办法是安装wps，然后利用wps的公式编辑器在viso中进行公式输入，但是字符的美观性有点差强人意。

所以这里推荐了开源的Inkscape作为viso的替代品。因为是开源的，所以Inkscape也有很多功能强大的插件可以用来满足不同使用者的需求，比如插入LaTeX公式。

### 目录

- 安装
- 安装LaTeX插件
- 测试


## 安装Inkscape

Inkscape支持Mac, Linux和Windows平台，2020年的最新版本为0.92.5。对于windows，直接[下载](https://inkscape.org/release/inkscape-0.92.5/)之后安装即可。

## 安装LaTeX插件

这里用到的Inkscape的LaTeX插件有两个：[TeXText](https://textext.github.io/textext/) 和 [WriteTeX](https://writetex.tk/)。

### LaTeX环境

在正式安装TexText和WriteTex之前，需要确保电脑有LaTex编译环境。对于Windows，需要预先安装[MikTeX](https://miktex.org/download)和[GSview](https://www.ghostscript.com/download/gsdnld.html).相对于其他的TeX发行版本（比如CTeX和TeXLive）来说，MikTeX有一个更为强大的包管理器。

### 安装TexText和WriteTex

安装所需要的所有文件可以直接在这里进行下载：[Inkscape.zip](http://bbs.sciencenet.cn/home.php?mod=attachment&filename=Inkscape.zip&id=443952)。下载之后进行解压。

* **安装pstoedit**, 直接在Inkscape.zip解压之后的文件夹中找到pstoeditsetup350.exe，双击安装即可。

* **安装TexText和pdf2svg**：

    * 将解压文件中的pdf2svg文件夹复制到`C: Program Files`文件夹，并添加到系统路径中（我的电脑右击，属性，高级系统设置，高级，环境变量，系统变量里边的Path）；

    * 双击pdf2svg文件夹中的pdf2svg.exe进行安装；

    * 双击运行文件中的TeXText文件夹中的setup_win.bat批处理文件，若最后显示“successful”则安装成功；

* **解压site-packages.zip**，将所有文件放置在inkscape安装目录文件夹下（一般在C盘，比如`C:\Program Files (x86)\Inkscape\Lib\Python2.7\site-packages`）；

*  **复制TexText.py**，将文件放到Inkscape extensions文件夹下（比如`C:\Program Files\Inkscape\share\extensions`）；

* **解压WriteTeX.zip**，将所有文件放到Inkscape extensions文件夹下（比如`C:\Program Files\Inkscape\share\extensions`）；

## 测试

安装完成之后，在Inkscape的主菜单下的扩展中选择TexText或者WriteTex，然后输入LaTex表达式，点击确认：

![Inkscape_code.JPG](https://i.loli.net/2020/04/13/48qtkxFZeUwhObz.jpg?imageView/2/w/619/q/90)

![Inkscape_result.JPG](https://i.loli.net/2020/04/13/pS5L3HleB7IzuwK.jpg?imageView/2/w/619/q/90)