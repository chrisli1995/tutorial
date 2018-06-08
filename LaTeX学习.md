## LaTeX学习

### 1 配置教程

基本配置：

https://blog.csdn.net/jenyzhang/article/details/78271711

设置PDF的反向搜索：

https://www.jianshu.com/p/4eb3e8ae2b66

### 2 学习视频

链接：https://pan.baidu.com/s/1nOsbveknFBwvHekQRQpNYg 密码：tisi

视频中有一些问题，一切以文档为准。

### 3 基础学习

LaTeX的源文件主要分为两个区域，导言区和正文区。

导言区用于全局的设置，在导言区设置好后，需要在正文区进行引用才能显示出来。通过改变\documentclass的类型，可以转换不同的文档格式。还可以通过加入$ $的方式在里面输入数学公式（使用$$ $$的话可以另起一行）。换行的话，只需要在两句话之间再加入一格的空行就行了。

默认是不支持中文的，所以需要通过\usepackage{ctex}命令引入ctex包，并在documentclass处声明utf8。或者设置\documentclass{ctexart}。

设置字体可以如title和author中那样加入\heiti、\kaishu。

在公式的前后加入\begin{equation} \end{equation}可以实现在公式后面加入序号，更系统的公式编写教材在第四章有讲。

```
%导言区
\documentclass[UTF8]{article}%book,report,letter
\usepackage{ctex}

\title{my first document\heiti我的第一个文档}
\author{\kaishu lwd}

%正文区(文稿区)
\begin{document}
	\maketitle
	hello world

	let $f(x)$ be definded by the formula
	$f(x)=3x^2+x-1$
	or

	$$f(x)=x_1^2$$

	or
	\begin{equation} 
	AB^2=BC^2+AC^2
	\end{equation}
	like this
\end{document}
```

### 4 公式编写

希望在这里直接使用LaTeX编译出文档，对照代码来学习。里面的有些用法同样适用于markdown。

\verb|符号| 的方式可以实现在文本中加入符号（是数学模式所以要加$等符号）。

#### 4.1 数学公式基础

```
\documentclass[UTF8]{article}%book,report,letter
\usepackage{ctex}

\begin{document}
	\section{简介}
	将排版内容分为文本模式和数学模式。文本模式用于普通排版，数学模式用于公式排版
	\section{行内公式}
	\subsection{美元符号（推荐使用这种）}
	比如$a+b=1+2$
	\subsection{小括号}
	比如\(a+b=1+2\)
	\subsection{math环境}
	比如\begin{math}a+b=1+2\end{math}
	\section{上下标}
	\subsection{上标}
	比如$3x^{20}-x+2=0$，使用上标符号的时候后面可以用大括号来决定上标的内容
	\subsection{下标}
	比如$a_0,a_{10}$
	\section{希腊字符}
	这个直接到https://blog.csdn.net/tmylzq187/article/details/51595970上去查找

	举个栗子$\alpha^3+\beta^2+\gamma=0$ 
	\section{数学函数}
	可以查看https://blog.csdn.net/garfielder007/article/details/51646604这个博客

	比如$\sqrt[4]{x}$
	\section{分式}
	有两种方式，一种是3/5，另一种是$\frac{3}{5}$ 
	\section{行间公式}
	\subsection{双美元符号}
	比如$$a+b=1+2$$
	\subsection{中括号}
	比如\[a+b=1+2\]
	\subsection{math环境}
	比如\begin{displaymath}a+b=1+2\end{displaymath}
	\subsection{自动编号equation}
	可以使用label去找到相应公式\ref{eq:test1}
	\begin{equation}
		a+b=b+a \label{eq:test1} 
	\end{equation}
	在equation的后面加入*号后则不会出现编号
\end{document}
```

#### 4.2 矩阵

输入矩阵需要导入amsmath包，需要注意矩阵输入一样是要放入数学模式的，下面是一些实例。

注意矩阵用&分隔列，用\\\分隔行，下面是具体的实现，可以对照latex生成的pdf来学习。

```
\documentclass[UTF8]{ctexart}
\usepackage{amsmath}

\begin{document}
	矩阵环境中，用\&分隔列，用$\backslash\backslash$分隔行,$\verb|{}|$

	$
	%无定界符
	\begin{matrix}
		0&1 \\
		1&0
	\end{matrix}
	%小括号
	\begin{pmatrix}
		0&1 \\
		1&0
	\end{pmatrix}
	%中括号
	\begin{bmatrix}
		0&1 \\
		1&0
	\end{bmatrix}
	%大括号
	\begin{Bmatrix}
		0&1 \\
		1&0
	\end{Bmatrix}
	%行列式
	\begin{vmatrix}
		0&1 \\
		1&0
	\end{vmatrix}
	%范数
	\begin{Vmatrix}
		0&1 \\
		1&0
	\end{Vmatrix}
	%行内小矩阵，需要自己手动加括号
	\left(
	\begin{smallmatrix}
		x&-y\\
		y&x
	\end{smallmatrix}
	\right)
	$


%如何写省略号和矩阵的维度,cdots或者dots是横省略号，ddots是斜省略号，vdots是竖省略号
	$
	A=\begin{bmatrix}
		a_{11}&\cdots&a_{1n}\\
		&\ddots&\vdots\\
		0&&a_{nn}
	\end{bmatrix}_{n\times n }
	$


%分块矩阵的编辑
	$
	\begin{pmatrix}
		\begin{matrix}1&0\\0&1\end{matrix}
		&\text{\Large 0}\\
		\text{\Large 0}&
		\begin{matrix}1&0\\0&-1\end{matrix}
	\end{pmatrix}
	$


%三角矩阵的编辑
	$
	\begin{pmatrix}
		a_{11}&a_{12}&\dots&a_{1n}\\
		&a_{22}&\dots&a_{2n}\\
		&&\ddots&\vdots\\
		\multicolumn{2}{c}{\Huge 0}&&a_{nn}
	\end{pmatrix}
	$

%跨列的省略号:\hdotsfor{<列数>}
	$
	\begin{pmatrix}
	1&\frac 12&\dots&\frac 1n\\
	\hdotsfor{4}\\
	m&\frac m2&\dots&\frac mn
	\end{pmatrix}
	$

%array环境（类似于表格环境）
	$
	\begin{array}{r|r}
	\frac12&0\\
	\hline
	0&-\frac ab c\\
	\end{array}
	$
\end{document}
```

