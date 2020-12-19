# 学习笔记

## 正则表达式
exec() 方法在一个指定字符串中执行一个搜索匹配。返回一个结果数组或 null。

在设置了 global 或 sticky 标志位的情况下（'g'/'y'），JavaScript RegExp 对象是**有状态的**。他们会将上次成功匹配后的位置记录在 lastIndex 属性中。使用此特性，exec() 可用来对单个字符串中的多次匹配结果进行逐条的遍历（包括捕获到的匹配）。在不设置的情况下，即使改变了手动修改lastIndex也不会影响匹配结果。而相比之下， String.prototype.match() 只会返回匹配到的结果。

## 编译原理

[流程](https://pic3.zhimg.com/80/v2-2ff01b00533c7d5bb25cc66f5c174baa_720w.jpg)

### 词法分析

>  `词法分析(Lexical Analyzer)`是第一个步骤，它也被称为 `扫描(scanning)`。词法分析器通过读入外部的字符流对其进行扫描，并且把它们组成有意义的`词素(lexeme)`序列，对于每个词素，词法分析器都会产生`词法单元(token)` 作为输出。这个词法单元会传递给下一个步骤，也就是语法分析。

利用正则表达式可以处理词法分析。

### 语法分析

> 第二个步骤是 `语法分析(syntax analysis)` 或者称为 `解析(parsing)`。语法分析器使用由词法分析器生成的各个词法单元的第一个分量来创建树形的中间表示。常用的方法就是 `语法树(syntax tree)`。编译器的后续步骤都会使用这个语法结构来帮助分析源程序，并声称目标程序。

* 产生式：定义的推导规则，就是从非终结符出发去构造串的方法。定义了非终结符的分解规则
* 终结符：和非终结符相对应，可以叫做是"语法常量"，已经被完全确定下来了
* 非终结符："语法变量"。在识别或者产生的过程中，如果该符号还未确定下来，还可以被继续推导，那么就是非终结符。

#### LL(k)分析算法

前k个元素的组合只能对应一个产生式

例子中终结符：Number、Operator
非终结符：AdditiveExpression、MultiplicativeExpression

* 巴科斯范式(BNF: Backus-Naur Form)

产生式

```
<AdditiveExpression> ::=
  <MultiplicativeExpression>
  <AdditiveExpression>(+|-)<MultiplicativeExpression>

<MultiplicativeExpression> ::=
  <Number>
  <MultiplicativeExpression>(*|/)<Number>
```

个人理解的四则运算产生式
```
<AdditiveExpression> ::=
  <Number>(+|-)<Number>
  <Number>(+|-)<MultiplicativeExpression>
  <MultiplicativeExpression>(+|-)<Number>
  <MultiplicativeExpression>(+|-)<MultiplicativeExpression>
  <AdditiveExpression>(+|-)<Number>
  <AdditiveExpression>(+|-)<MultiplicativeExpression>

<MultiplicativeExpression> ::=
  <Number>(*|/)<Number>
  <MultiplicativeExpression>(*|/)<Number>
```
