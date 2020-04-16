---
layout:     post
title:      LaTeX论文写作
subtitle:   来自Haifeng的建议
date:       2020-04-15
author:     Haifeng
header-img: img/sunflower.jpg
catalog: true
music-id: 28815250
tags:
    - LaTeX
    - Overleaf
---

<!--
网易云音乐：《平凡之路》
-->

时间如梭，不知不觉在德国的学习时间已经过去了整整2年半，到了该考虑毕业论文的时候了😂。

## 国内外软件使用的不同

有一点感触颇深的是国内外对科研工具使用的不同：国外个人基本上用到的全是开源的工具，而国内更习惯使用成熟的商业软件。比如在国内我们会使用ARCGIS来浏览处理一些遥感图像，而在国外采用的对应工具则为 [QGIS](https://qgis.org/en/site/)，[VICAR](https://github.com/nasa/VICAR/) 和 [GDAL](https://gdal.org/); 国内用 ARCGIS 来绘制地理图，国外用到的则是 [GMT](http://gmt.soest.hawaii.edu/)；国内倾向于使用 word，wps 来写文章写项目，而国外用到的则是 [Overleaf 线上编辑神器](https://www.overleaf.com/)或者 MikTeX+TexStudio 等线下编辑器, 但是Overleaf已经集成了各种环境了，所以加载包之后直接就可以用了；国内利用 EDARS LPS aATE 或者 [ENVI](https://www.harrisgeospatial.com/Software-Technology/ENVI) 等来处理立体像对以生成数字高程模型，而在国外对应的则是 [ISIS3 Jigsaw](http://isis.astrogeology.usgs.gov/) 和 [Ames Stereo Pipeline](https://ti.arc.nasa.gov/tech/asr/groups/intelligent-robotics/ngt/stereo/)。还有好多例子以后有机会再说, 有时间也跟大家分享下这些软件的使用经验（keng）。

### 不同的主要原因

国外个人多利用开源软件的原因在我看来觉得主要是这么几条：

* **没钱买**。现在很多商业软件是需要付费的，而且对于一些特有的功能的话收费是非常高的。这点可以从国外的书籍价格中略知一二（在德国的话平均都是30欧左右，大约300 RMB）。

* **对盗版的打击力度很大**。德国是非常重视知识产权的国家，如果在网上非法下载电影都有可能被查，然后收到来自慕尼黑一家私人公司的罚单。罚单有的甚至可以达到1000欧以上（取决于你非法下载的电影的数量）。

* **Linux系统的普及**。很多德国的科研机构使用的都是Linux系统，同时会有专门的运维师傅（以学校为例，一般一个小的系差不多配备一个运维工程师）负责安装和更新同事需要的开源软件和依赖库，然后会使用文件共享系统来充分利用Linux电脑和服务器的资源。所以很多时候你需要的开源环境已经在那里了，直接用就是了！有了bug也可以直接邮件运维师傅了，省下了不少精力，可以让你专注于科研项目。

## LaTeX论文写作注意点

扯的有点远了，我其实是想利用这篇文章来跟大家探讨下利用LaTeX论文写作时的一些注意事项😄:

* 正文中在引用图片和公式时均需要用“~”来产生空格，比如`Fig.~\ref{fig:PAM_processing}`和`Eq.~\eqref{eq:L3x3}`。这样的好处是使得被引部分（比如Fig.和Eq.）和引用标记（比如5，（6））在换行时不会发生错开而分出两行的错误或者不美观情况。

* 使用Mendeley等文献管理工具来管理论文和导出Bib TeX文件，因为直接从谷歌学术或者百度学术中导出来的Bib文件不会包含doi项，需要人工手动添加进去。另外，从这些学术引擎中导出来的Bib文件的标题没有加上{}，从而LaTeX编译之后显示出来的，除了标题的第一个字母大写，全是小写的（比如：`title = {Development of the Laser Altimeter (LIDAR) for Hayabusa2}` 会在参考文献列表中显示为 `Development of the laser altimeter (lidar) for hayabusa2`）。但是对于学术文献，我们希望的是保持原始的样式，而Mendeley则会在导出的Bib title项中自动加上{} （比如：`title = {{Development of the Laser Altimeter (LIDAR) for Hayabusa2}}` 编译之后会在参考文献列表中显示为 `Development of the Laser Altimeter (LIDAR) for Hayabusa2`）。

* 学会利用Mathpix公式截取工具来进行LaTex公式的“公式截图-复制LaTeX代码-粘贴”，使用超级简单。具体可以参见[知乎上的介绍](https://www.zhihu.com/question/35931336/answer/641198933)。另外由于LaTeX对表格不是特别友好，这里推荐另一款专门生成表格的神奇：[Tables Generator](http://www.tablesgenerator.com/latex_tables)，使用也是非常简介高效。Tables Generator是一个在线制作LaTeX, HTML和Markdown格式的表格代码工具，支持在表格中编辑数据，修改字体/颜色填充，对齐方式等等。

* 在论文投稿时，可以直接去论文的官方网站寻找相应的LaTeX写作模板（bst文件，cls文件等），然后将这些文件加载进本地工程文件夹，之后在开头和结尾分别利用`\documentclass{cls model}`和`\bibliographystyle{bst model}`语句来引用这些外部文件即可。以Journal of Geodesy为例，LaTeX模板可以在[这里](https://www.springer.com/journal/190/updates/17232314)找到，其实和其他的Spring出版的格式差不多，都是svjour3.cls和spbasic.bst等（作为对比Elsvier出版杂志很多时候用到的是elsarticle.cls和model5-names.bst）。另外利用LaTeX文件向[Editorial Manager (EM)](https://www.editorialmanager.com/joge/default.aspx)投稿的时候的一些说明和注意事项可以在[这里](https://static.springer.com/sgw/documents/1667815/application/pdf/190_Special%20Guidelines%20from%20EiC.pdf)找到，包括EM支持的LaTeX环境，投稿时LaTeX不同文件类型的正确顺利等，有一点奇怪的就是EM居然不支持自定义宏，这点有点让人费解。

* 在使用多层分式嵌套的时候，使用`\dfrac`代替`\frac`会使得公式变的好看不拥挤。但是得加上amsmath包：`\usepackage{amsmath}`。比如以下使用`\frac`的公式：
  ```latex
  % defined own marcos
  \newcommand{\scli}[2]{#1_{\mathrm{\small #2}}}
  \newcommand{\sclut}[3]{#1_{\mathrm{\small #2}}^{\mathrm{\small #3}}}

  % utlizing \frac{}{}
  \begin{equation}
  \begin{aligned}
      t_2-t_1=\frac{r_{12}}{c}
      &+
      \frac{(1+\gamma)\scli{\mu}{S}}{c^3}\ln
      \begin{bmatrix}
      \frac{\sclut{r}{1}{S}+\sclut{r}{2}{S}+\sclut{r}{12}{S}
      +\frac{(1+\gamma)\scli{\mu} {S}}{c^2}}{\sclut{r}{1}{S}
      +\sclut{r}{2}{S}+\sclut{r}{12}{S}
      +\frac{(1+\gamma)\scli{\mu}{S}}{c^2}}\\
      \end{bmatrix}\\
      &+
      \sum_{\mathrm{B}=1}^{n}\frac{(1+\gamma)\scli{\mu}{B}}{c^3}\ln
      \begin{bmatrix}
      \frac{\sclut{r}{1}{B}+\sclut{r}{2}{B}+\sclut{r}{12}{B}}
      {\sclut{r}{1}{B}+\sclut{r}{2}{B}-\sclut{r}{12}{B}}\\
      \end{bmatrix}
       +\mathcal{O}(c^{-5})\,.
  \end{aligned}
  \label{eq:LightTimeSolution}
  \end{equation}
  ```
  编译之后变成：
  ![formula0.JPG](https://i.loli.net/2020/04/16/jpJwWSAnd1CgZaO.jpg =200x)
  而将`\frac{}{}`改为`\dfrac{}{}`之后，则变为：
  ![formula1.JPG](https://i.loli.net/2020/04/16/UzYAVtgawxsQmWj.jpg)
  是不是漂亮了不少？另外有关于怎么利用LaTex打出漂亮的公式，这里有本非常赞的中文资料可以供大家来参考：<u>ChinaTeXMathFAQ_V11.pdf</u>, 大家可以直接去百度搜索就可以找得到。

* 根据文章不同的章节来制作对应的.tex文件，然后在main.tex（专门用来加载格式文件，一些需要的包，文章的作者和摘要等）使用`\input{chapter.tex}`来进行加载。这样做的好处是使得文章的段落条理清晰，也方便了编辑时的查找和快速定位（对于Overleaf在生成的pdf中双击需要编辑的位置，也会自动转到对应的tex文件那里）。如果文章包含的图片文件太多，也可以建立一个pics文件夹，然后把图片全部放到里，引用时只需更改相应的路径名就行，比如：`\includegraphics[scale=0.35]{pics/pic_name.pdf}`。对于参考文献可以全部放到一个ref_name.bib文件里边，然后使用`\bibliographystyle{bst model}; \bibliography{ref_name}`来进行调用。

* 在文章投稿时，会要就加上相应的行列号，这时候就会用到lineno包（放在`\begin{document}`前边）：
  ```latex
  % adding line numbers for reviewing
  \usepackage{lineno}
  \linenumbers
  % 行号标记的间隔
  \modulolinenumbers[1]
  % 行号的字体颜色等
  \renewcommand{\linenumberfont}{\normalfont\bfseries\small\color{red}}
  ```
  另外一个技巧是，在利用`\begin{equation}; \end{equation}`编写公式的时候需要用`\begin{linenomath*}; \end{linenomath*}`来将公式代码括起来，这样单独的公式也会被列入行号。<u>更重要的是</u>，如果没有这样做的话，生成的行号很可能是不连续的，错误的！拿之前的那个公式做个列子：
  ```latex
  % defined own marcos
  \newcommand{\scli}[2]{#1_{\mathrm{\small #2}}}
  \newcommand{\sclut}[3]{#1_{\mathrm{\small #2}}^{\mathrm{\small #3}}}

  % utlizing \frac{}{}
  \begin{linenomath*}
  \begin{equation}
  \begin{aligned}
      t_2-t_1=\frac{r_{12}}{c}
      &+
      \frac{(1+\gamma)\scli{\mu}{S}}{c^3}\ln
      \begin{bmatrix}
      \frac{\sclut{r}{1}{S}+\sclut{r}{2}{S}+\sclut{r}{12}{S}
      +\frac{(1+\gamma)\scli{\mu} {S}}{c^2}}{\sclut{r}{1}{S}
      +\sclut{r}{2}{S}+\sclut{r}{12}{S}
      +\frac{(1+\gamma)\scli{\mu}{S}}{c^2}}\\
      \end{bmatrix}\\
      &+
      \sum_{\mathrm{B}=1}^{n}\frac{(1+\gamma)\scli{\mu}{B}}{c^3}\ln
      \begin{bmatrix}
      \frac{\sclut{r}{1}{B}+\sclut{r}{2}{B}+\sclut{r}{12}{B}}
      {\sclut{r}{1}{B}+\sclut{r}{2}{B}-\sclut{r}{12}{B}}\\
      \end{bmatrix}
       +\mathcal{O}(c^{-5})\,.
  \end{aligned}
  \label{eq:LightTimeSolution}
  \end{equation}
  \end{linenomath*}
  ```

* 未完待续。。。想到了继续写。其他的一些点参见阅读资源中的第一个链接。


>### 阅读资源

>- [LaTeX写作新手须知](https://weibo.com/ttarticle/p/show?id=2309403955741387052924)
>- [最全 Markdown + Latex 编写技巧](https://blog.csdn.net/HaleyPKU/article/details/80341932)
>- [Python下使用matplotlib库时,如何与LaTeX结合起来？](https://www.zhihu.com/question/55035983/answer/142312872)
>- [Inkscape插入LaTeX公式到矢量图中](https://haifengtub.github.io/2020/04/13/inkscape/)
>- [UESTC LaTeX毕设论文模板 Overleaf无痛上手指南](https://zhuanlan.zhihu.com/p/126712982)
>- [在线 LaTeX 编辑网站overleaf.com加载缓慢解决办法](https://zhuanlan.zhihu.com/p/108974887)
>- [MikTex+TexStudio配置论文写作环境](https://zhuanlan.zhihu.com/p/42844087)
