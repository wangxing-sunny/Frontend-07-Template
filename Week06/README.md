# 学习笔记

## 乔姆斯基谱系

语言分为：

* 非形式语言，如汉语、英语等
* 形式语言，计算机编程语言都是形式语言

计算机科学中刻画形式语言文法表达能力的一个分类谱系，由诺姆·乔姆斯基于1956年提出。包括四个层次：

* 0-型文法（无限制文法、短语结构文法）包括所有的文法
* 1-型文法（上下文相关文法）生成上下文相关语言
* 2-型文法（上下文无关文法）生成上下文无关语言
* 3-型文法（正规文法）生成正则语言（可被正则表达式描述？）

[图灵机（Turing machine）](https://zh.wikipedia.org/wiki/图灵机)：又称确定型图灵机，是英国数学家艾伦·图灵于 1936 年提出的一种将人的计算行为抽象掉的数学逻辑机，其更抽象的意义为一种计算模型，可以看作等价于任何有限逻辑数学过程的终极强大逻辑机器。

[图灵完备性](https://zh.wikipedia.org/wiki/圖靈完備性)：在可计算性理论里，如果一系列操作数据的规则（如指令集、编程语言、细胞自动机）可以用来模拟单带图灵机，那么它是图灵完全的。这个词源于引入图灵机概念的数学家艾伦·图灵。虽然图灵机会受到储存能力的物理限制，图灵完全性通常指“具有无限存储能力的通用物理机器或编程语言”。

终结符： 最终在代码中出现的字符（[ https://zh.wikipedia.org/wiki/ 終結符與非終結符](https://zh.wikipedia.org/wiki/終結符與非終結符))

产生式： 在计算机中指 Tiger 编译器将源程序经过词法分析（Lexical Analysis）和语法分析（Syntax Analysis）后得到的一系列符合文法规则（Backus-Naur Form，BNF）的语句

静态和动态语言：[ https://www.cnblogs.com/raind/p/8551791.html](https://www.cnblogs.com/raind/p/8551791.html)

强类型： 无隐式转换

弱类型： 有隐式转换

协变与逆变：[ https://jkchao.github.io/typescript-book-chinese/tips/covarianceAndContravariance.html](https://jkchao.github.io/typescript-book-chinese/tips/covarianceAndContravariance.html)