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


 
