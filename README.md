# LaTeX
Study notes of LaTex

---
## 特殊符号

 - `$`：数学模式符号
 - `%`：注释符号
 - `^`:上标符号
 - `{}`：分组符号
 - `\`：宏命令
 - `~`：带子（用于一些不可隔行的空格，比如名称与编号之间的空格：Question 2）
 - `#`：用于宏定义
 - `&`：用于表格对齐
 - `_`：数学模式下标
 - **要在正文中使用这些需要在前面加`\`，`\`需要写成`\textbackslash`，`^`需要写成`\^{}`，`~`需要写成`\~{}`，`_`需要写成`\_{}`**

## 常见用法
 - 连字符：`-`
 - 数字范围：`--`
 - 破折号（——）：`---`
 - ~：`$\sim$`
 - ...：`\ldots` or `\dots`
 - 句中使用省略号：`$\ldots$`（使用数学模式）
 - 幻影：`\phantom{参数}`
 
## 字体设置
### 字体族设置（罗马，无衬线，打字机）
 - `\textrm{}` `\textsf{}` `\texttt{}`
 - `{\rmfamily  }` `{\sffamily  }` `{\ttfamily  }`
### 字体系列设置（粗细，宽度）
 - `\textmd{}` `\textbf{}`
 - `{\mdseries  }` `{\bfseries  }`
### 字体形状设置（直立，斜体，伪斜体，小型大写）
 - `\textup{}` `\textit{}` `\textsl{}` `\textsc{}`
 - `{\upshape  }` `{\itshape  }` `{\slshape  }` `{\scshape  }`
### 中文字体设置（宋体，黑体，仿宋，楷体）
 - `{\songti  }` `{\heiti  }` `{\fangsong  }` `{\kaiti  }`
 - `\textbf{粗体 黑体表示}` `\textit{斜体 楷体表示}`
### 字体大小设置
 - **导言区可以设置：`\documentclass[10pt]{article}`(一般只有10-12pt)**
 - `{\tiny  }`
 - `{\scripysize  }`
 - `{\footnotesize  }`
 - `{\small  }`
 - `{\normalsize  }`
 - `{\large  }`
 - `{\Large  }`
 - `{\LARGE  }`
 - `{\huge  }`
 - `{\Huge  }`
 - **中文字号设置：`\zihao{5}`**
 - **设置字号的时候在导言区设置（newcommand），在正文区使用**

## 空格设置

 - 两个quad空格（两个m的宽度）：	`a \qquad b` 
 - quad空格（一个m的宽度）： `a \quad b`	
 - 1/6个m宽度：`\thinspace` 
 - 1/6m宽度：`\enspace`
 - 大空格（1/3m宽度）： `a\ b` 
 - 中等空格（2/7m宽度）：	`a\;b` 
 - 小空格（1/6m宽度）: `a\,b` 
 - 紧贴（缩进1/6m宽度）： `a\!b` 
 - 1pc = 12pt = 4.218mm
 - 长度可以为负值：`a\kern -1em b` or `a\kern 1pc b`
 - `a\hskip 1em b`
 - `a\hspace{35pt} b`
 - 占位宽度：`a\hphantom{xyz} b`
 - 弹性长度：`a\hfill b`


## 插图
 - 导言区：`\usepackage{graphicx}`
 - 语法：`\includegraphics[< 选项 >]{< 文件名 >}`
 - 格式：EPS，PDF，PNG，JPEG，BMP
 - 图片在当前目录下的figures和PICS目录下：`\graphicspath{{figures/},{pics
 - 在正文中插入图片：

```
\begin{document}
    \LaTex{}
    设置缩放比例
    \includegraphics[scale=0.3]{lion}
    设置高度
    \includegraphics[height=0.3cm]{lion}
    设置宽度
    \includegraphics[width=0.3cm]{lion}
    设置版型高度
    \includegraphics[height=0.3cm]{lion}
    设置版型宽度
    \includegraphics[width=0.3cm]{lion}
\end{document}
```

## 表格

```
\begin{document}
    生成五列表格，分别是左对齐，居中，居中，右对齐和指定宽度(自动换行)
    \begin{tabular}{l || c | c | r | p{1.5cm}}
        姓名 & 语文 & 数学 & 外语 & 备注 \\
        \hilne \hilne 两个命令可以产生双横线
        姓名 & 语文 & 数学 & 外语 & 备注 \\
        \hilne
        姓名 & 语文 & 数学 & 外语 & 备注 \\
        \hilne
        姓名 & 语文 & 数学 & 外语 & 备注 \\
        \hilne
    \end{tabular}
\end{document}
```

## 浮动体

```
\begin{document}
    交叉引用
    \LaTeX{}中\Tex系统吉祥物见图\ref{fig-lion}
    
    \begin{figure}
        图片居中
        \centering
        \includegraphics[scale=0.3]{lion}
        设置图片标题并且设置标签
        \caption{\Tex 吉祥物}\label{fig-lion}
    \end{figure}
    
    \begin{table}
        表格居中
        \centering
        设置图片标题
        \caption{考试成绩单}
        
        \begin{tabular}{l || c | c | r | p{1.5cm}}
            姓名 & 语文 & 数学 & 外语 & 备注 \\
        \end{tabular}
        
    \end{table}
    
\end{document}
```


 - `\begin{figure}[<允许位置>]`
 - <允许位置>参数（默认tbp）
 - - h: 此处（here）-代码所在的上下文
 - - t: 页顶（top）-代码所在页面或者之后页面的顶部
 - - b: 页底（bottom）-代码所在页面或之后页面的底部
 - - p: 独立一页（page）-浮动页面
 - 标题控制：caption和bicaption等宏包
 - 并排与子图表：subcaption，subfig和floatrow等宏包
 - 绕排：picinpar和wrapfig等宏包
 - 注意：应该合理使用交叉引用而不是硬编码。

## 数学公式

### 行内公式

* `$ a+b=b+a $`
* `\( a+b=b+a \)`
* `\begin{math} a+b=b+a \end{math}`

### 上下标

#### 上标

- `$3x^{20} - x + 2 = 0$`

#### 上标

- `$a_0, a_1, A_{100x+2}$`

### 希腊字母

- `$\alpha$`
- `$\beta$`
- `$\gamma$`
- `$\epsilon$`
- `$\pi$`
- `$\Gamma$`
- `$\Delta$`
- `$\Theta$`
- `$\Pi$`
- `$\Omega$`

### 数学函数

- `$\log$`
- `$\sin$`
- `$\cos$`
- `$\arcsin$`
- `$\arccos$`
- `$\sqrt{2}$`

### 分式

- `$3/4$`
- `$\frac{3}{4}$`

### 行间公式

- `比例是 $$\frac{3}{4}$$`
- `比例是 \[frac{3}{4}\]`
- `比例是 \begin{displaymath} frac{3}{4} \end{displaymath}`
- 对公式进行自动编号并且对公式进行交叉引用：

```
交换律见式\ref{eq:commutative}
\begin{equation}
    a+b=b+a \label{eq:commutative}
\end{equation}
```

- 对公式不进行自动编号并且对公式进行交叉引用（需要amsmath宏包）：

```
交换律见式\ref{eq:commutative}
\begin{equation*}
    a+b=b+a \label{eq:commutative}
\end{equation*}
```

### 矩阵（需要amsmath宏包）


```
\begin{document}
    \[
    \begin{matrix}
        0 & 1 \\
        1 & 0 
    \end{matrix}
    \]
\end{document}
```


* 加入小括号
`\begin{pmatrix}`
`\end{pmatrix}`

* 加入中括号
`\begin{bmatrix}`
`\end{bmatrix}`

* 加入大括号
`\begin{Bmatrix}`
`\end{Bmatrix}`

* 加入单竖线
`\begin{vmatrix}`
`\end{vmatrix}`

* 加入双竖线
`\begin{Vmatrix}`
`\end{Vmatrix}`

* 矩阵中的上下标：`\a_{11}^2`

* 矩阵中的省略号：`\dots` `\vdots` `\ddots` `\adots`

* 矩阵中的跨列省略号：`\hdotsfor{<列数>}`

* 矩阵整体下标：
`\end{bmatrix}_{n \times n}`

* 矩阵行内小矩阵（smallmatrix）

* array环境排版更为复杂的环境

### 多行公式（需要amsmath和amssymb宏包）

```
\begin{document}
    % 用gather（带编号）和gather*（不带编号）环境（可以使用\\换行）
    \begin{gather}
        a+b=b+a \\
        ab ba
    \end{gather}
    
    % 在\\之前使用\notag阻止编号
    \begin{gather}
        a+b=b+a \notag \\
        ab ba
    \end{gather}
    
    % 用align环境按照指定位置对齐（align*不对公式进行编号），对齐位置由&决定
    \begin{align}
        a+b&=b+a \\
        ab& ba
    \end{align}
    
    % 用split环境将公式进行多行排版
    \begin{split}
        a+b& \\
        =b+a
    \end{split}
\end{document}
```

## 参考文献——BibTex

### 一次管理，一次使用

```
\begin{thebibliography}
    \bibitem[记号]{引用标志}文献条目1
    %使用`\emph`标重
    \bibitem{article1}陈立辉,苏伟.\emph{基于LaTeX的Web数学公式提取方法研究}[J]. 计算机科学。 2014(06)
    %使用`\texttt`引用链接
    \bibitem{latexGuide}Kopka,Patrick.\emph{Guide to \LaTeX}, $4^{th}$ Edition. Available at \texttt{http://www.amazon.com}
\end{thebibliography}
```

* **使用`\cite{article1}`引用文章**

### 一次管理，多次使用

```
@BOOK{引用标志,
    title = {},
    publisher = {},
    year = {},
    author = {},
    series = {},
    address = {},
    adition = {}
}
```


* **使用`\bibliographystyle{plain}`指定样式**

* **正文中使用：**
```
\begin{document}
    \bibliography{引用标志}
\end{document}
```
* **排版未引用的文献：`\nocite{*}`**


## 参考文献——BibLaTex

```
\usepackage[style=numeric,backend=biber]{biblatex}
\addbibresource{test.bib}

%正文区
\begin{document}
    %一次管理，多次引用
    无格式化引用\cite{biblatex}
    带方括号的引用\parencite{a1-1}
    上标引用\supercite{6-1}
    %列出未引用文献
    \nocite{*}
    \printbibliography[title = {参考文献}]
\end{document}
```

## 命令的定义与重定义

* **内容与格式分离的思想**

```
%导言区
\documentclass{ctexart}（或者ctexbook, ctexrep）
%\newcommand-定义命令
%命令只能由字母组成，不能以\end开头
%\newcommand<命令>[<参数个数>][<手参数默认值>]{<具体定义>}
```

* **例如：使用\PRC 相当于 People's Pepublic of \emph{China}**

```
\newcommand\PRC{People's Republic of \emph{China}}

%正文区（文稿区）
\begin{docuemnt}
    \PRC
\end{document}
```

* **\newcommand还可以添加参数，参数个数从1-9，使用时前添加#**

```
\newcommand\loves[2]{#1 喜欢 #2}

%正文区（文稿区）
\begin{docuemnt}
    \loves{猫儿}{鱼儿}
\end{document}
```

* **为\newcommand添加默认参数值**

```
\newcommand\loves[3][喜欢]{#2#1#3}

%正文区（文稿区）
\begin{docuemnt}
    %输出猫儿喜欢鱼儿
    \loves{猫儿}{鱼儿} 
    
    %输出猫儿最爱鱼儿
    \loves[最爱]{猫儿}{鱼儿}
\end{document}
```

* **使用\renewcommand\abstractname重定义命令**

* **使用\newenvironment定义环境**

```
%\newenvironment{<环境名称>}[<参数个数>][<首参数默认值>]
%    {<环境前定义>}
%    {<环境后定义>}
    
\newenvironment{myabstract}[1][摘要]
{\small
    \begin{center}\bfseries #1\end{center}
    \begin{quotation}}
    {\end{quotation}}
```


* **使用\renewenvironment重定义环境**

* **\newenvironment和\newcommand嵌套使用**

```
\newenvironment{Quotation}[1]
{\newcommand\quotesource{#1}
    \begin{quotation}}
    {\par\hfill--- 《\textit{\quotesource}》
    \end{quotation}}   
    
\begin{document}
    \begin{Quotation}{乾卦}
        初九，潜龙勿用。
    \end{Quotation}
\end{document}
```

* **文章结构内容参考：** https://www.bilibili.com/video/av16002978/
