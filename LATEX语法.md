TEX 是Donald E. Knuth 编写的一个以排版文章及数学公式为目标的计算机程序。

LATEX 目前使用最广泛的TEX 宏集。 每一个LATEX 命令实际上最后都会被转换解释成几个甚至上百个TEX命令。

**数学公式基本语法**

**1.上标与下标**

上标命令是 ^{角标}，下标命令是 _{角标}。当角标是单个字符时可以不用花括号（在 LaTeX 中，花括号是用于分组，即花括号内部文本为一组）。

```latex
$$x_1$$
$$x_1^2$$
$$x^2_1$$
$$x_{22}^{(n)}$$
$${}^*\!x^*$$    %（“\!” 表示其前后字符之间无间隙）
```

$$x_1$$
$$x_1^2$$
$$x^2_1$$
$$x_{22}^{(n)}$$
$${}^*\!x^*$$    %（“\!” 表示其前后字符之间无间隙）

**2.分式**

输入较短的分式时，最简单的方法是使用斜线，譬如输入 (x+y)/2，

要输入带有水平分数线的公式，可用命令：\frac{分子}{分母}。

```latex
$$\frac{x+y}{2}$$
$$\frac{1}{1+\frac{1}{2}}$$
```

$$\frac{x+y}{2}$$
$$\frac{1}{1+\frac{1}{2}}$$

**3.根式**

排版根式的命令是：开平方：\sqrt{表达式}；开 n 次方：\sqrt[n]{表达式}

```latex
$$\sqrt{2}<\sqrt[3]{3}$$
$$\sqrt{1+\sqrt[p]{1+a^2}}$$
$$\sqrt{1+\sqrt[^p\!]{1+a^2}}$$
```

$$\sqrt{2}<\sqrt[3]{3}$$
$$\sqrt{1+\sqrt[p]{1+a^2}}$$
$$\sqrt{1+\sqrt[^p\!]{1+a^2}}$$

**4 求和与积分**

排版求和符号与积分符号的命令分别为 \sum 和 \int，它们通常都有上下限，在排版上就是上标和下标。

```latex
$$\sum_{k=1}^{n}\frac{1}{k}$$
$\sum_{k=1}^n\frac{1}{k}$
$$\int_a^b f(x)dx$$
$\int_a^b f(x)dx$
微分符直体：$$\int_a^b f(x)\mathrm{d}x$$
```

$$\sum_{k=1}^{n}\frac{1}{k}$$
$\sum_{k=1}^n\frac{1}{k}$
$$\int_a^b f(x)dx$$
$\int_a^b f(x)dx$
微分符直体：$$\int_a^b f(x)\mathrm{d}x$$

在数学模式中，TEX 根据上下文选择字体大小。例如，上标会排版成较小的字体。如果你想要把等式的一部分排版成罗马字体，不要用\textrm 命令，只因\textrm 会暂时切换到文本模式， 而此时字体大小切换机制将不起作用。使用\mathrm 来保持字体大小切换机制的正常

**5.公式中的空格**

LaTeX 能够自动处理公式中的大多数字符之间的空格，但是有时候需要自己手动进行控制。

```latex
紧贴 $a\!b$
没有空格 $ab$
小空格 a\,b
中等空格 a\;b
大空格 a\ b
quad空格 $a\quad b$
两个quad空格 $a\qquad b$
```

紧贴 $a\!b$
没有空格 $ab$
小空格 a\,b
中等空格 a\;b
大空格 a\ b
quad空格 $a\quad b$
两个quad空格 $a\qquad b$

注意:不同的TEX解析器给出的结果稍有不同

在公式中灵活的运用空格命令可以起到美化公式的作用。

```latex
$$\int_a^b f(x)\mathrm{d}x$$
插入小空格：$$\int_a^b f(x)\,\mathrm{d}x$$
```

$$\int_a^b f(x)\mathrm{d}x$$
插入小空格：$$\int_a^b f(x)\,\mathrm{d}x$$

**6 公式中的定界符**

这里所谓的定界符是指包围或分割公式的一些符号

```latex
$($    %(
$)$    %)
$[$    %[
$]$    %]
$\{$    %{
$\}$    %}
$|$    %|
$\|$    %||
```

$($    
$)$   
$[$    
$]$    
$\{$   
$\}$    
$|$   
$\|$

在上述这些定界符之前冠以 \left（修饰左定界符）或 \right（修饰右定界符），可以得到自适应缩放的定界符，它们会根据定界符所包围的公式大小自适应缩放。

```latex
$$\left(\sum_{k=\frac{1}{2}}^{N^2}\frac{1}{k}\right)$$
```

$$\left(\sum_{k=\frac{1}{2}}^{N^2}\frac{1}{k}\right)$$

**7 矩阵**

对于少于 10 列的矩阵，可使用 matrix，pmatrix，bmatrix，Bmatrix，vmatrix 和 Vmatrix 等环境。

```latex
$$\begin{matrix}1 & 2\\3 &4\end{matrix}$$
$$\begin{pmatrix}1 & 2\\3 &4\end{pmatrix}$$
$$\begin{bmatrix}1 & 2\\3 &4\end{bmatrix}$$
$$\begin{Bmatrix}1 & 2\\3 &4\end{Bmatrix}$$
$$\begin{vmatrix}1 & 2\\3 &4\end{vmatrix}$$
$$\begin{Vmatrix}1 & 2\\3 &4\end{Vmatrix}$$
```

$$\begin{matrix}1 & 2\\3 &4\end{matrix}$$
$$\begin{pmatrix}1 & 2\\3 &4\end{pmatrix}$$
$$\begin{bmatrix}1 & 2\\3 &4\end{bmatrix}$$
$$\begin{Bmatrix}1 & 2\\3 &4\end{Bmatrix}$$
$$\begin{vmatrix}1 & 2\\3 &4\end{vmatrix}$$
$$\begin{Vmatrix}1 & 2\\3 &4\end{Vmatrix}$$

**8 排版数组**

当矩阵规模超过 10 列，或者上述矩阵类型不敷需求，可使用 `array` 环境。该环境可把一些元素排列成横竖都对齐的矩形阵列。

```latex
$$
\mathbf{X} =
\left( \begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ddots
\end{array} \right)
$$
```

$$
\mathbf{X} =
\left( \begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ddots
\end{array} \right)
$$

\mathbf大写控制符，\\表示换行，{ccc}表示列样式。array 环境也可以用来排版这样的表达式，表达式中使用一个“.” 作为其隐藏的\right 定界符。

```latex
$$
y = \left\{ \begin{array}{ll}
a & \textrm{if $d>c$}\\
b+x & \textrm{in the morning}\\
l & \textrm{all day long}
\end{array} \right.
$$
```

$$
y = \left\{ \begin{array}{ll}
a & \textrm{if $d>c$}\\
b+x & \textrm{in the morning}\\
l & \textrm{all day long}
\end{array} \right.
$$

你也可以在array 环境中画线，如分隔矩阵中元素。

```latex
$$
\left(\begin{array}{c|c}
1 & 2 \\
\hline
3 & 4
\end{array}\right)
$$
```

$$
\left(\begin{array}{c|c}
1 & 2 \\
\hline
3 & 4
\end{array}\right)
$$