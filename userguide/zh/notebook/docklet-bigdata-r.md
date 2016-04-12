
# 一个R语言实现的爬虫，爬取拉手网美食信息


```R
library(XML)

giveNames = function(rootNode){
  names <- xpathSApply(rootNode,"//h3/a[@class='goods-name']",xmlValue)
  names
}

givesevices = function(rootNode){
  sevices <- xpathSApply(rootNode,"//h3/a[@class='goods-text']",xmlValue)
  sevices
}


giveprices = function(rootNode){
  prices <- xpathSApply(rootNode,"//div/span[@class='price']",xmlValue)
  prices
}


givemoney = function(rootNode){
  money <- xpathSApply(rootNode,"//div/span[@class='money']",xmlValue)
  money
}


giveplaces = function(rootNode){
  places <- xpathSApply(rootNode,"//a/span[@class='goods-place']",xmlValue)
  places
}


getmeituan = function(URL){
  Sys.sleep(runif(1,1,2))
  doc<-htmlParse(URL[1],encoding="UTF-8")
  rootNode<-xmlRoot(doc)
  data.frame(
    Names=giveNames(rootNode), #店名
    services=givesevices(rootNode), #服务
    prices=giveprices(rootNode),  #现价
    money=givemoney(rootNode),  #原价
    places=giveplaces(rootNode)  #地点
    
  )
}


URL = paste0("http://shenzhen.lashou.com/cate/meishi/page",1:10)

mainfunction = function(URL){
  data = rbind(
    getmeituan (URL[1]),
    getmeituan (URL[2]),
    getmeituan (URL[3]),
    getmeituan (URL[4]),
    getmeituan (URL[5])
  )
  
  
}
ll=mainfunction(URL)
write.table(ll,"result.txt",row.names=FALSE)
ll

```

# R语言的线性回归实例

输入数据


```R
#读入数据
x<- c(0.10,0.11,0.12,0.13,0.14,0.15,0.16,0.17,0.18,0.20,0.21,0.23)
y<-c(42.0,43.5,45.0,45.5,45.0,47.5,49,53,50,55,55,60)
#绘出 x 与 y 的散列图
plot(y~x)
```

在终端中执行该段代码，即可看到输出图形；从图中我们可以看出 y 和 x 存在线性相关性，可以进行线性回归分析：


```R
model<-lm(y~x)
summary(model)
```

我们通过 P 值(就是上面的 pr 那一列)来查看对应的解释变量 x 的显著性，通过将 p 值与 0.05 进行比较，若改值小于 0.05，就可以说该变量与被解释变量存在显著的相关性。

Multiple R-squared 和 Adjusted R-squared 这两个值，就是我们常称为”拟合优度“和”修正的拟合优度“，是指回归方程对样本的拟合程度，这里我们可以看到，修正的拟合优度为 0.9429，表示拟合程度超过五成，这个值越高越好。

最后，看下 F-statistic，也就是常说的 F 统计量，也称为 F 检验，常用语判断方程整体的显著性实验，其 p 值为 9.505e-08，显然小于 0.05，我们可以认为方程在 P=0.05 的水平上是通过显著性检验的。

从上面我们看出我们的线性回归效果不错，那么我们可以利用拟合方程进行分类，或者预测。


```R
newX<-data.frame(x=0.16)
predict(model,newdata=newX,interval="prediction",level=0.95)#interval=”prediction“ level指定预测的置信区间
```

# R语言的逻辑回归示例


```R
counts <- c(18,17,15,20,10,20,25,13,12)
outcome <- gl(3,1,9)
treatment <- gl(3,3)
print(d.AD <- data.frame(treatment, outcome, counts))
glm.D93 <- glm(counts ~ outcome + treatment, family = poisson())
anova(glm.D93)
summary(glm.D93)
```


```R

```
