<html>
<head><meta charset="utf-8" />
<title>BalancingReactions</title>

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

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="&#37197;&#24179;&#21270;&#23398;&#26041;&#31243;&#24335;">&#37197;&#24179;&#21270;&#23398;&#26041;&#31243;&#24335;<a class="anchor-link" href="#&#37197;&#24179;&#21270;&#23398;&#26041;&#31243;&#24335;">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h6 id="The-latest-version-of-this-IPython-notebook-is-available-at-http://github.com/jckantor/CBE20255--for-noncommercial-use-under-terms-of-the-Creative-Commons-Attribution-Noncommericial-ShareAlike-License.">The latest version of this IPython notebook is available at <a href="http://github.com/jckantor/CBE20255">http://github.com/jckantor/CBE20255</a>  for noncommercial use under terms of the <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution Noncommericial ShareAlike License</a>.<a class="anchor-link" href="#The-latest-version-of-this-IPython-notebook-is-available-at-http://github.com/jckantor/CBE20255--for-noncommercial-use-under-terms-of-the-Creative-Commons-Attribution-Noncommericial-ShareAlike-License.">&#182;</a></h6><p>J.C. Kantor (Kantor.1@nd.edu)</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="&#20363;1--&#30002;&#28919;&#29123;&#28903;">&#20363;1  &#30002;&#28919;&#29123;&#28903;<a class="anchor-link" href="#&#20363;1--&#30002;&#28919;&#29123;&#28903;">&#182;</a></h3><p>甲烷(<img src="http://www.forkosh.com/mathtex.cgi? \( CH_4\)"> ) 燃烧的反应如下：</p>

<img src="http://www.forkosh.com/mathtex.cgi? CH_4 + O_2 \rightarrow CO_2 + H_2O">

<br />
我们要寻找一组计量系数来配平这个反应式。计量系数<img src="http://www.forkosh.com/mathtex.cgi? \(\nu_s\)">是一组和物质s对应的系数，使得反应式可以写成下面的形式：

<img src="http://www.forkosh.com/mathtex.cgi? \nu_{CH_4}CH_4 + \nu_{O_2}O_2 + \nu_{CO_2}CO_2 + \nu_{H_2O}H_2O = 0">

<br/>负化学计量系数对应于反应物，正化学计量系数对应于该反应的产物。计量系数应使得反应前后各物质中原子守恒。如果反应中有带电物质，还应保证电荷守恒。
<br/>计算计量系数可以使用 <a href="http://sympy.org/en/index.html">SymPy</a> 包
可以为参与反应的每种物质设一个计量系数，并用计量系数表示出原子守恒条件。

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="kn">import</span> <span class="nn">sympy</span>

<span class="n">sympy</span><span class="o">.</span><span class="n">var</span><span class="p">([</span><span class="s1">&#39;vCH4&#39;</span><span class="p">,</span> <span class="s1">&#39;vO2&#39;</span><span class="p">,</span> <span class="s1">&#39;vCO2&#39;</span><span class="p">,</span> <span class="s1">&#39;vH2O&#39;</span><span class="p">])</span>

<span class="n">atomBalances</span> <span class="o">=</span> <span class="p">[</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vCH4</span> <span class="o">+</span> <span class="n">vCO2</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span>             <span class="c1"># Carbon 碳原子</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">4</span><span class="o">*</span><span class="n">vCH4</span> <span class="o">+</span> <span class="mi">2</span><span class="o">*</span><span class="n">vH2O</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span>         <span class="c1"># Hydrogen 氢原子</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">2</span><span class="o">*</span><span class="n">vO2</span> <span class="o">+</span> <span class="o">+</span><span class="mi">2</span><span class="o">*</span><span class="n">vCO2</span> <span class="o">+</span> <span class="n">vH2O</span><span class="p">,</span><span class="mi">0</span><span class="p">)</span>   <span class="c1"># Oxygen 氧原子</span>
<span class="p">]</span>

<span class="k">for</span> <span class="n">eqn</span> <span class="ow">in</span> <span class="n">atomBalances</span><span class="p">:</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">eqn</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>vCH4 + vCO2 == 0
4*vCH4 + 2*vH2O == 0
2*vCO2 + vH2O + 2*vO2 == 0
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
<p>还有一种独特的方法：给反应指定一个<em>basis</em>. basis是一个额外的方程，用来指定其中一种物质的化学计量系数。我们不妨将甲烷的计量系数设为-1</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">basis</span> <span class="o">=</span> <span class="p">[</span><span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vCH4</span><span class="p">,</span><span class="o">-</span><span class="mi">1</span><span class="p">)]</span>

<span class="k">for</span> <span class="n">eqn</span> <span class="ow">in</span> <span class="n">atomBalances</span> <span class="o">+</span> <span class="n">basis</span><span class="p">:</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">eqn</span><span class="p">)</span>

<span class="n">sympy</span><span class="o">.</span><span class="n">solve</span><span class="p">(</span><span class="n">atomBalances</span> <span class="o">+</span> <span class="n">basis</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>vCH4 + vCO2 == 0
4*vCH4 + 2*vH2O == 0
2*vCO2 + vH2O + 2*vO2 == 0
vCH4 == -1
</pre>
</div>
</div>

<div class="output_area"><div class="prompt output_prompt">Out[2]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>{vH2O: 2, vCO2: 1, vO2: -2, vCH4: -1}</pre>
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
<h3 id="&#20363;2--&#19968;&#20010;&#33258;&#29123;&#21453;&#24212;">&#20363;2  &#19968;&#20010;&#33258;&#29123;&#21453;&#24212;<a class="anchor-link" href="#&#20363;2--&#19968;&#20010;&#33258;&#29123;&#21453;&#24212;">&#182;</a></h3><p><div style="float: right; margin: 10px; width: 160px; font-size: 80%; line-height: 120%;">

</div>
自燃是一类自发产生的燃烧反应。自燃推进器是这类反应的一种常见应用。</p>
<p>一个例子是由SpaceX公司开发的SuperDraco引擎使用的甲基肼（MMH）和氧化剂四氧化二氮的自燃反应。</p>
<p><strong>未配平</strong>的反应式如下：</p>
<img src="http://www.forkosh.com/mathtex.cgi? CH_6N_2 + N_2O_4 \rightarrow CO_2 + NO + H_2O">

<p>下面我们计算计量系数配平反应式。考虑如下问题：一千克燃料需要多少氧化剂？</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Identify unknown stoichiometric coefficients</span>
<span class="n">sympy</span><span class="o">.</span><span class="n">var</span><span class="p">([</span><span class="s1">&#39;vCH6N2&#39;</span><span class="p">,</span><span class="s1">&#39;vN2O4&#39;</span><span class="p">,</span><span class="s1">&#39;vCO2&#39;</span><span class="p">,</span><span class="s1">&#39;vNO&#39;</span><span class="p">,</span><span class="s1">&#39;vH2O&#39;</span><span class="p">])</span>

<span class="c1"># Atom balances</span>
<span class="n">eqns</span> <span class="o">=</span> <span class="p">[</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">1</span><span class="o">*</span><span class="n">vCH6N2</span> <span class="o">+</span> <span class="n">vCO2</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span>                <span class="c1"># Carbon</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">6</span><span class="o">*</span><span class="n">vCH6N2</span> <span class="o">+</span> <span class="mi">2</span><span class="o">*</span><span class="n">vH2O</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span>              <span class="c1"># Hydrogen</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">4</span><span class="o">*</span><span class="n">vN2O4</span> <span class="o">+</span> <span class="mi">2</span><span class="o">*</span><span class="n">vCO2</span> <span class="o">+</span> <span class="n">vNO</span> <span class="o">+</span> <span class="n">vH2O</span><span class="p">,</span><span class="mi">0</span><span class="p">),</span>  <span class="c1"># Oxygen</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">2</span><span class="o">*</span><span class="n">vN2O4</span> <span class="o">+</span> <span class="n">vNO</span><span class="p">,</span><span class="mi">0</span><span class="p">)</span>                   <span class="c1"># Nitrogen</span>
<span class="p">]</span>

<span class="c1"># Basis</span>
<span class="n">eqns</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vCH6N2</span><span class="p">,</span><span class="o">-</span><span class="mi">1</span><span class="p">))</span>

<span class="k">for</span> <span class="n">eqn</span> <span class="ow">in</span> <span class="n">eqns</span><span class="p">:</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">eqn</span><span class="p">)</span>

<span class="n">soln</span> <span class="o">=</span> <span class="n">sympy</span><span class="o">.</span><span class="n">solve</span><span class="p">(</span><span class="n">eqns</span><span class="p">)</span>
<span class="nb">print</span> <span class="p">(</span><span class="s2">&quot;</span><span class="se">\n</span><span class="s2">Stoichiometric Coefficients: &quot;</span><span class="p">,</span> <span class="n">soln</span><span class="p">)</span>

<span class="n">mwN2O4</span> <span class="o">=</span> <span class="mf">92.011</span>
<span class="n">mwCH6N2</span> <span class="o">=</span> <span class="mf">46.07</span>

<span class="n">nCH6N2</span> <span class="o">=</span> <span class="mf">1.0</span><span class="o">/</span><span class="n">mwCH6N2</span>                         <span class="c1"># kg-mol of MMH</span>
<span class="n">nN2O4</span> <span class="o">=</span>  <span class="p">(</span><span class="n">soln</span><span class="p">[</span><span class="n">vN2O4</span><span class="p">]</span><span class="o">/</span><span class="n">soln</span><span class="p">[</span><span class="n">vCH6N2</span><span class="p">])</span><span class="o">*</span><span class="n">nCH6N2</span>   <span class="c1"># kg-mol of N2O4</span>
<span class="n">mN2O4</span> <span class="o">=</span> <span class="n">mwN2O4</span><span class="o">*</span><span class="n">nN2O4</span>                         <span class="c1"># kg of N2O4</span>

<span class="nb">print</span> <span class="p">(</span><span class="s2">&quot;</span><span class="se">\n</span><span class="s2">{0:7.3f} kilograms of N2O4 required per kilogram of CH6N2&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">mN2O4</span><span class="p">))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>vCH6N2 + vCO2 == 0
6*vCH6N2 + 2*vH2O == 0
2*vCO2 + vH2O + 4*vN2O4 + vNO == 0
2*vN2O4 + vNO == 0
vCH6N2 == -1

Stoichiometric Coefficients:  {vN2O4: -5/2, vH2O: 3, vCH6N2: -1, vCO2: 1, vNO: 5}

  4.993 kilograms of N2O4 required per kilogram of CH6N2
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
<h3 id="&#20363;3--&#19968;&#20010;&#27700;&#28342;&#28082;&#20013;&#26377;&#30005;&#33655;&#36716;&#31227;&#30340;&#21453;&#24212;">&#20363;3  &#19968;&#20010;&#27700;&#28342;&#28082;&#20013;&#26377;&#30005;&#33655;&#36716;&#31227;&#30340;&#21453;&#24212;<a class="anchor-link" href="#&#20363;3--&#19968;&#20010;&#27700;&#28342;&#28082;&#20013;&#26377;&#30005;&#33655;&#36716;&#31227;&#30340;&#21453;&#24212;">&#182;</a></h3>

<br/>金属镉<img src="http://www.forkosh.com/mathtex.cgi? Cd">溶解于浓硝酸，生成<img src="http://www.forkosh.com/mathtex.cgi? Cd^{+2}">离子和一氧化氮(<img src="http://www.forkosh.com/mathtex.cgi?  NO">).
<br />反应式如下：
<br />
<img src="http://www.forkosh.com/mathtex.cgi?  Cd + NO_3^- \longrightarrow Cd^{+2} + NO">

<br />
观察两侧的电荷，这个反应式显然无法直接配平。
<br />对于这类反应，我们需要考虑水和溶液中的离子。配平反应式，我们考虑下面的8种物质：

<br/>
<img src="http://www.forkosh.com/mathtex.cgi?  Cd,\ H_2O,\ HNO_3,\ NO,\ Cd^{+2},\ H^+,\ OH^-,\ NO_3^-">
<br/>
设8个计量系数。接下来写出原子守恒的约束条件（4个，对应4种原子），电荷守恒约束条件（1个），并将<img src="http://www.forkosh.com/mathtex.cgi? Cd">的计量系数指定为1（指定basis，1个）：

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Identify unknown stoichiometric coefficients</span>
<span class="n">v</span> <span class="o">=</span> <span class="n">sympy</span><span class="o">.</span><span class="n">var</span><span class="p">([</span><span class="s1">&#39;vCd&#39;</span><span class="p">,</span><span class="s1">&#39;vH2O&#39;</span><span class="p">,</span><span class="s1">&#39;vHNO3&#39;</span><span class="p">,</span><span class="s1">&#39;vNO&#39;</span><span class="p">,</span><span class="s1">&#39;vCdpos2&#39;</span><span class="p">,</span><span class="s1">&#39;vHpos&#39;</span><span class="p">,</span><span class="s1">&#39;vOHneg&#39;</span><span class="p">,</span><span class="s1">&#39;vNO3neg&#39;</span><span class="p">])</span>

<span class="c1"># Atom balances</span>
<span class="n">eqns</span> <span class="o">=</span> <span class="p">[</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vCd</span> <span class="o">+</span> <span class="n">vCdpos2</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>                             <span class="c1"># Cadmium</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">2</span><span class="o">*</span><span class="n">vH2O</span> <span class="o">+</span> <span class="n">vHNO3</span> <span class="o">+</span> <span class="n">vHpos</span> <span class="o">+</span> <span class="n">vOHneg</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span>           <span class="c1"># Hydrogen</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vH2O</span> <span class="o">+</span> <span class="mi">3</span><span class="o">*</span><span class="n">vHNO3</span> <span class="o">+</span> <span class="n">vNO</span> <span class="o">+</span> <span class="n">vOHneg</span> <span class="o">+</span> <span class="mi">3</span><span class="o">*</span><span class="n">vNO3neg</span><span class="p">,</span> <span class="mi">0</span><span class="p">),</span> <span class="c1"># Oxygen</span>
    <span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vHNO3</span>  <span class="o">+</span> <span class="n">vNO</span> <span class="o">+</span> <span class="n">vNO3neg</span><span class="p">,</span> <span class="mi">0</span><span class="p">)</span>                     <span class="c1"># Nitrogen</span>
<span class="p">]</span>

<span class="c1"># Charge balance</span>
<span class="n">eqns</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="mi">2</span><span class="o">*</span><span class="n">vCdpos2</span> <span class="o">+</span> <span class="n">vHpos</span> <span class="o">-</span> <span class="n">vOHneg</span> <span class="o">-</span> <span class="n">vNO3neg</span><span class="p">,</span> <span class="mi">0</span><span class="p">))</span>

<span class="c1"># Basis</span>
<span class="n">eqns</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vCd</span><span class="p">,</span> <span class="o">-</span><span class="mi">1</span><span class="p">))</span>

<span class="k">for</span> <span class="n">eqn</span> <span class="ow">in</span> <span class="n">eqns</span><span class="p">:</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">eqn</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>vCd + vCdpos2 == 0
2*vH2O + vHNO3 + vHpos + vOHneg == 0
vH2O + 3*vHNO3 + vNO + 3*vNO3neg + vOHneg == 0
vHNO3 + vNO + vNO3neg == 0
2*vCdpos2 + vHpos - vNO3neg - vOHneg == 0
vCd == -1
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

这里，变量数多于方程数，因此有一定的<em>自由度（degrees of freedom）</em>。我们需要做出额外的假设。
<br />我们假设在浓硝酸中，硝酸完全电离，即有 <img src="http://www.forkosh.com/mathtex.cgi? \nu_{HNO_3}=0">.

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">eqns</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vHNO3</span><span class="p">,</span> <span class="mi">0</span><span class="p">))</span>
<span class="n">sympy</span><span class="o">.</span><span class="n">solve</span><span class="p">(</span><span class="n">eqns</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[5]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>{vHpos: vOHneg - 8/3,
 vCd: -1,
 vNO: 2/3,
 vCdpos2: 1,
 vH2O: -vOHneg + 4/3,
 vHNO3: 0,
 vNO3neg: -2/3}</pre>
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

其中6个计量系数已经确定，但还存在水和 <img src="http://www.forkosh.com/mathtex.cgi? \nu_{OH^-}"> 计量系数的依赖关系。考虑水的电离：<br>
<img src="http://www.forkosh.com/mathtex.cgi? H_2O \longrightarrow H^+ + OH^-">
<br/>
我们令 <img src="http://www.forkosh.com/mathtex.cgi? \nu_{H_2O} = 0">

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">sympy</span><span class="o">.</span><span class="n">solve</span><span class="p">(</span><span class="n">eqns</span> <span class="o">+</span> <span class="p">[</span><span class="n">sympy</span><span class="o">.</span><span class="n">Eq</span><span class="p">(</span><span class="n">vH2O</span><span class="p">,</span><span class="mi">0</span><span class="p">)])</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[6]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>{vOHneg: 4/3,
 vHpos: -4/3,
 vCd: -1,
 vNO: 2/3,
 vCdpos2: 1,
 vH2O: 0,
 vNO3neg: -2/3,
 vHNO3: 0}</pre>
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
<p>到此，给出了平衡的反应式：</p>

<img src="http://www.forkosh.com/mathtex.cgi? Cd + \frac{4}{3}\,H^+ + \frac{2}{3}\,NO_3^- \longrightarrow Cd^{+2} + \frac{4}{3}\,OH^- + \frac{2}{3}\,NO "> 

</div>
</div>
</div>
    </div>
  </div>
</body>
</html>

