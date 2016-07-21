<html>
<head><meta charset="utf-8" />
<title>TheMatrixExponential</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>


<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}

@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

</head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="&#30697;&#38453;&#25351;&#25968;">&#30697;&#38453;&#25351;&#25968;<a class="anchor-link" href="#&#30697;&#38453;&#25351;&#25968;">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>By <a href="http://www.maths.manchester.ac.uk/~srelton/">Sam Relton</a></p>
<p>这个notebook简要介绍了矩阵指数，一个在应用数学诸多领域有着广泛应用的有趣的函数。在给出其定义之后，还介绍了一些应用和算法。
<br />注：算法部分介绍了一种可用但相对错误率表现一般的基本算法，此外作者在文末列举了可供使用的软件和进一步阅读的资料，这些内容这里没有收录；微分方程实例后的进一步说明也略去了，可以<a href="http://nbviewer.jupyter.org/github/sdrelton/matrix_function_notebooks/blob/master/TheMatrixExponential.ipynb">参阅原文</a></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="&#23450;&#20041;">&#23450;&#20041;<a class="anchor-link" href="#&#23450;&#20041;">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">scipy</span> <span class="k">as</span> <span class="nn">sp</span>
<span class="kn">import</span> <span class="nn">scipy.linalg</span> <span class="k">as</span> <span class="nn">la</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
矩阵指数是相应的标量函数的直接推广。请记住\(\exp(x)\)的泰勒级数展开：
<br />
$$\exp(x) = \sum_{k = 0}^\infty \frac{x^k}{k!}$$

<br />我们可以利用矩阵乘法将它应用到方阵：
<br />
$$\exp(A) = \sum_{k = 0}^\infty \frac{A^k}{k!}$$
<br />矩阵指数的2个最有用的属性是：
<br />$$\exp((a + b)A) = \exp(aA)\exp(bA)$$
<br />
且当两个矩阵A和B满足AB = BA时,<br />
$$\exp(A + B) = \exp(A)\exp(B)$$

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="&#24212;&#29992;">&#24212;&#29992;<a class="anchor-link" href="#&#24212;&#29992;">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>矩阵指数在包括癌症研究、核燃耗方程、计算机图形学等领域有着广泛而多样的应用。
我们将看两个应用实例：线性微分方程的求解和复杂网络中重要节点的发现。</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="&#24494;&#20998;&#26041;&#31243;">&#24494;&#20998;&#26041;&#31243;<a class="anchor-link" href="#&#24494;&#20998;&#26041;&#31243;">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>矩阵指数的一个大亮点是，能够直接给出微分方程的解：
$$y'(t) = A y(t),\qquad y(0) = y_0$$
<br />
对于 \(y, y_0 \in \mathbb{C}^n\)
且 \(A \in \mathbb{C}^{n \times n}\)
<br />
解为：
<br/>
\(y(t) = \exp(At) y_0\)
<br/>知道这一点，我们可以直接地计算y(t)的解，而不必使用像欧拉方法那样的时间步进方法。
让我们看一个简单的例子：
<br/>
$$y'(t) = \begin{bmatrix} 1 & -20 \\ 3 & 4 \\ \end{bmatrix} y(t), \qquad y(0) = \begin{bmatrix}1\\0\end{bmatrix},\qquad t \in [0, 1]$$



</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="kn">import</span> <span class="nn">scipy.integrate</span> <span class="k">as</span> <span class="nn">sint</span>

<span class="n">A</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([[</span><span class="mi">1</span><span class="p">,</span> <span class="o">-</span><span class="mi">20</span><span class="p">],</span>
              <span class="p">[</span><span class="mi">3</span><span class="p">,</span> <span class="mi">4</span><span class="p">]],</span> <span class="n">dtype</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">double</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">yprime</span><span class="p">(</span><span class="n">y</span><span class="p">,</span> <span class="n">t</span><span class="p">):</span>
    <span class="k">return</span> <span class="n">sp</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">A</span><span class="p">,</span> <span class="n">y</span><span class="p">)</span>

<span class="n">t</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">51</span><span class="p">)</span>
<span class="n">yzero</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">])</span>

<span class="c1"># Solve equation using odeint</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">sint</span><span class="o">.</span><span class="n">odeint</span><span class="p">(</span><span class="n">yprime</span><span class="p">,</span> <span class="n">yzero</span><span class="p">,</span> <span class="n">t</span><span class="p">)</span> <span class="c1"># Calls the Fortran library odeint</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">y</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">],</span> <span class="n">y</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">])</span> <span class="c1"># Blue line is y(t) for t in [0, 1]</span>

<span class="n">plt</span><span class="o">.</span><span class="n">xlim</span><span class="p">([</span><span class="o">-</span><span class="mi">4</span><span class="p">,</span> <span class="mi">9</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylim</span><span class="p">([</span><span class="o">-</span><span class="mi">3</span><span class="p">,</span> <span class="mi">5</span><span class="p">])</span>

<span class="c1"># Solve for 10 t values using the exponential</span>
<span class="n">tvals</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">11</span><span class="p">)</span>

<span class="k">for</span> <span class="n">tval</span> <span class="ow">in</span> <span class="n">tvals</span><span class="p">:</span>
    <span class="n">yval</span> <span class="o">=</span> <span class="n">sp</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">la</span><span class="o">.</span><span class="n">expm</span><span class="p">(</span><span class="n">A</span><span class="o">*</span><span class="n">tval</span><span class="p">),</span> <span class="n">yzero</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">yval</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">yval</span><span class="p">[</span><span class="mi">1</span><span class="p">],</span> <span class="s1">&#39;rs&#39;</span><span class="p">)</span> <span class="c1"># Red squares are evaluated via the matrix exponential</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
AElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="&#32593;&#32476;&#20013;&#30340;&#37325;&#35201;&#33410;&#28857;">&#32593;&#32476;&#20013;&#30340;&#37325;&#35201;&#33410;&#28857;<a class="anchor-link" href="#&#32593;&#32476;&#20013;&#30340;&#37325;&#35201;&#33410;&#28857;">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>矩阵指数可以用于寻找网络中最具影响的节点。
所谓网络，包括一组<strong>节点</strong>，以及一组连接这些节点的<strong>边</strong>。我们使用邻接矩阵来描述一个网络。
<br />
若节点i，j之间有边，则\(A_{ij} = 1\)，否则\(A_{ij} = 0\)
<br />我们考虑下面的矩阵：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="kn">import</span> <span class="nn">networkx</span> <span class="k">as</span> <span class="nn">nx</span>

<span class="n">Adj</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">],</span> 
                <span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">],</span> 
                <span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">],</span> 
                <span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">],</span> 
                <span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">],</span>
                <span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">]])</span>

<span class="n">G</span> <span class="o">=</span> <span class="n">nx</span><span class="o">.</span><span class="n">from_numpy_matrix</span><span class="p">(</span><span class="n">Adj</span><span class="p">)</span>
<span class="n">nx</span><span class="o">.</span><span class="n">draw</span><span class="p">(</span><span class="n">G</span><span class="p">,</span> <span class="n">node_color</span><span class="o">=</span><span class="s1">&#39;y&#39;</span><span class="p">,</span> <span class="n">node_size</span><span class="o">=</span><span class="mi">1000</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
ERERg/0/EyJBYWj8WPoAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>衡量网络中节点重要性的一个常用指标是<strong>中心度</strong>。用\(A^k_{ij}\)表示想哦那个节点i到节点j的长度为k的路径条数。我们可以如下计算节点i的中心度：将所有对中心度的贡献值（长度不等的由节点i到自身的路径数）相加</p>
\(c(i) = \alpha_1 A_{ii} + \alpha_2 A^2_{ii} + \alpha_3 A^3_{ii} + \cdots\)<p>这里的系数\(\alpha_k\)待定
一般而言，我们假定和长的路径相比，短路径更重要，因此\(\alpha_k \ge \alpha_{k+1}\).
已经有了许多计算系数\(\alpha_k\)的公式， 如果取<br/>
$$\alpha_k = \frac{1}{k!}$$
就有\(c(i) = \exp(A)\)</p>
<p>看我们之前给出的网络，我们直观上期望节点1就是那个最重要的节点:它的度数(degree)最大，而且与节点3, 4, 0, 2都相连。
<br />现在我们就来计算每个节点的中心度，并对这些节点按照重要性递减的顺序排序：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">centralities</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">diag</span><span class="p">(</span><span class="n">la</span><span class="o">.</span><span class="n">expm</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">Adj</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">double</span><span class="p">)))</span>
<span class="n">nodeorder</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">argsort</span><span class="p">(</span><span class="n">centralities</span><span class="p">)[::</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>

<span class="nb">print</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="n">nodeorder</span><span class="p">,</span> <span class="n">centralities</span><span class="p">[</span><span class="n">nodeorder</span><span class="p">]])</span>

<span class="c1"># Note: This is already built into networkx using the following command</span>
<span class="c1"># print nx.communicability_centrality_exp(G)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>[[ 1.          0.          2.          3.          4.          5.        ]
 [ 4.44723536  2.86427609  2.86427609  2.36018456  1.71615913  1.59432922]]
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>正如我们所预期的，节点1是最重要的节点.接下来是节点0和2，它们的中心度相同，交换这两个节点，图没有发生变化。</p>

</div>
</div>
</div>
    </div>
  </div>
</body>
</html>

