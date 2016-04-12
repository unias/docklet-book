<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. 使用docklet和R进行大数据分析</a>
<ul>
<li><a href="#sec-1-1">1.1. 在Docklet上使用R开发运行调试环境</a>
<ul>
<li><a href="#sec-1-1-1">1.1.1. 创建包含R workspace的容器</a></li>
</ul>
</li>
<li><a href="#sec-1-2">1.2. Docklet的R控制台</a>
<ul>
<li><a href="#sec-1-2-1">1.2.1. 文件操作</a></li>
<li><a href="#sec-1-2-2">1.2.2. R控制台</a></li>
<li><a href="#sec-1-2-3">1.2.3. linux终端</a></li>
</ul>
</li>
<li><a href="#sec-1-3">1.3. R语言的爬虫示例</a></li>
<li><a href="#sec-1-4">1.4. R语言的线性回归示例</a></li>
<li><a href="#sec-1-5">1.5. R语言的逻辑回归示例</a></li>
</ul>
</li>
</ul>
</div>
</div>

# 使用docklet和R进行大数据分析<a id="sec-1" name="sec-1"></a>

## 在Docklet上使用R开发运行调试环境<a id="sec-1-1" name="sec-1-1"></a>

### 创建包含R workspace的容器<a id="sec-1-1-1" name="sec-1-1-1"></a>

登陆docklet.sei.pku.edu.cn或者iwork.pku.edu.cn

进入docklet dashboard页面后，点击add workspace，使用默认的镜像即可（已包含R）

在danshboard页面点击start，只需要几十毫秒即启动成功，点击go，即进入workspace

## Docklet的R控制台<a id="sec-1-2" name="sec-1-2"></a>

### 文件操作<a id="sec-1-2-1" name="sec-1-2-1"></a>

进入workspace后，默认显示files标签页，这里显示您的个人文件。这些文件都保存在分布式文件系统上，并且只有您能访问，安全可靠。你可以通过upload上传您的代码和输入数据到该目录下，也可以把在这里的输出文件下载到本地。

点击右上角的new，在下拉框选择textFile，可以创建新文件，并进入编辑页面。编译页面提供了一个在线IDE，支持几乎所有主流语言。

### R控制台<a id="sec-1-2-2" name="sec-1-2-2"></a>

点击右上角的new，在下拉框选择R，即进入R语言的控制台。这是一个网页版的R控制台，和在linux输入R命令进入的控制台以及在windows打开R软件进入的控制台功能完全一样。

输入指令

    Sys.getenv()
    help(mean)
    ls.files()

进行测试，在web console中查看输入信息

### linux终端<a id="sec-1-2-3" name="sec-1-2-3"></a>

如果您在编辑和运行调试R程序的时候，需要执行一些linux命令，点击右上角的new，在下拉框选择terminal，即可打开一个在线linux ternimal

## R语言的爬虫示例<a id="sec-1-3" name="sec-1-3"></a>

我们使用编写了一个抓取美团上美食信息的爬虫，通过上述的文件上传步骤已经把代码上传到个人的workspace

以下部分的代码是用来访问网页，抓取相关信息的

    doc<-htmlParse(URL[1],encoding="UTF-8")
     rootNode<-xmlRoot(doc)
     data.frame(
       Names=giveNames(rootNode), #店名
       services=givesevices(rootNode), #服务
       prices=giveprices(rootNode),  #现价
       money=givemoney(rootNode),  #原价
       places=giveplaces(rootNode)  #地点
    
     )

以下部分代码用来解析xml信息，从中获取美食的名字信息

    library(XML)
    
    giveNames = function(rootNode){
      names <- xpathSApply(rootNode,"//h3/a[@class='goods-name']",xmlValue)
      names
    }

在上文介绍的R控制台中输入

    source("meituan.R")

并执行，控制台将显示结果数据，并且将数据写入了result.txt中，您可以在文件标签页查看该文件并下载。

## R语言的线性回归示例<a id="sec-1-4" name="sec-1-4"></a>

代码如下：

    #读入数据
    x<- c(0.10,0.11,0.12,0.13,0.14,0.15,0.16,0.17,0.18,0.20,0.21,0.23)
    y<-c(42.0,43.5,45.0,45.5,45.0,47.5,49,53,50,55,55,60)
    #绘出 x 与 y 的散列图
    plot(y~x)

在终端中执行该段代码，即可看到输出图形；从图中我们可以看出 y 和 x 存在线性相关性，可以进行线性回归分析：

    >model<-lm(y~1+x) #1 可以不写，代表截距项;如果写 -1 表示强制过原点
    >summary(model) #如下是此句输出
    Call:
    lm(formula = y ~ 1 + x)
    
    Residuals:
       Min      1Q  Median      3Q     Max
    -2.0431 -0.7056  0.1694  0.6633  2.2653
    
    Coefficients: #估计值  #标准差  #t 值 #p 值
               Estimate Std. Error t value Pr(>|t|)
    (Intercept)   28.493      1.580   18.04 5.88e-09 ***
    x            130.835      9.683   13.51 9.50e-08 ***
    ---
    Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
    
    Residual standard error: 1.319 on 10 degrees of freedom
    Multiple R-squared:  0.9481,    Adjusted R-squared:  0.9429
    F-statistic: 182.6 on 1 and 10 DF,  p-value: 9.505e-08

我们通过 P 值(就是上面的 pr 那一列)来查看对应的解释变量 x 的显著性，通过将 p 值与 0.05 进行比较，若改值小于 0.05，就可以说该变量与被解释变量存在显著的相关性。

Multiple R-squared 和 Adjusted R-squared 这两个值，就是我们常称为”拟合优度“和”修正的拟合优度“，是指回归方程对样本的拟合程度，这里我们可以看到，修正的拟合优度为 0.9429，表示拟合程度超过五成，这个值越高越好。

最后，看下 F-statistic，也就是常说的 F 统计量，也称为 F 检验，常用语判断方程整体的显著性实验，其 p 值为 9.505e-08，显然小于 0.05，我们可以认为方程在 P=0.05 的水平上是通过显著性检验的。

从上面我们看出我们的线性回归效果不错，那么我们可以利用拟合方程进行分类，或者预测。

    >newX<data.frame(x=0.16) #这里是输入数据，必须是frame类型
    >predict(model,newdata=newX,interval="prediction",level=0.95)#interval=”prediction“ level指定预测的置信区间
       fit      lwr      upr
    1 49.42639 46.36621 52.48657

## R语言的逻辑回归示例<a id="sec-1-5" name="sec-1-5"></a>

一个简单的示例:

    counts <- c(18,17,15,20,10,20,25,13,12)
    outcome <- gl(3,1,9)
    treatment <- gl(3,3)
    print(d.AD <- data.frame(treatment, outcome, counts))
    glm.D93 <- glm(counts ~ outcome + treatment, family = poisson())
    anova(glm.D93)
    summary(glm.D93)

在终端中输入以上代码，即可得到一个结果报告
