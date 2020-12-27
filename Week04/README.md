# 学习笔记

## Symbol

ES6引入的一种新的原始类型，表示***独一无二的值***；一般用来定义对象的唯一属性名，或者不需要关心值为多少的情景，所有使用可计算属性的地方都可以使用Symbol。

不能使用new Symbol方式创建Symbol对象，使用函数方式创建Symbol。Symbol函数接收一个可选参数，用于描述即将创建的Symbol。描述('Symbol("xx")')存放在[[Description]]属性中，但是不能直接访问。

使用Symbol.for()创建可共享的Symbol，接收一个即将创建的Symbol的字符串标识符。创建过程首先在***全局Symbol注册表***中搜索键是否存在，负责新创建一个Symbol并注册。Symbol.keyFor()在Symbol全局注册表中检索与Symbol有关的键。

Symbol值不可强制转换为字符串类型或数字类型。逻辑判断时等价于true。

```javascript
Symbol('a') === Symbol('a') // false
Symbol.for('a') === Symbol.for('a') // 'a' === 'a', true
```

特殊的Symbol：

### Symbol.hasInstance

任何class或者Function中都有的方法名称。`obj instanceof ClassA`等价于`ClassA[Symbol.hasInstance](obj)`。

本身是不可写不可枚举不可配置的属性；可以使用Object.defineProperty重新定义。

**待补充**

******



## 字典树(单词查找树)

特点：

* 根节点不包含字符，除根节点以外的每一个节点都只包含一个字符；
* 从根节点到某一个节点，路径上经过的字符连接起来，为该节点对应的字符串；
* 每个节点的所有子节点包含的字符都不相同；

利用字符串公共前缀来减少查询时间；查询效率比**哈希树**高。

## KMP

前缀表（prefix table）

前面字符的公共前后缀，比如字符串"abcabababc"，前缀表依次'a'，'ab'，'abc'，'**a**bc**a**'，'**ab**c**ab**'，'**a**bcab**a**'，'**ab**cab**ab**'，'**a**bcabab**a**'，'**ab**cabab**ab**'，'**abc**abab**abc**'的公共前后缀(均为从左向右看)，为[0, 0, 0, 1, 2, 1, 2, 1, 2, 3]。一般来说第i位用来表示前`i-1`位的公共前后缀，因此前缀表一般使用[0, 0, 0, 0, 1, 2, 1, 2, 1, 2]，最后一位忽略。

***TODO***
带通配符的KMP算法

## Wildcard Matching(通配符匹配)

思路第一个 * 前的字符完全匹配，除去最后一个 * 外其余的 * 尽可能少的匹配字符；最后一个 * 尽可能多的匹配字符。带 ? 的字符传可以替换为正则来处理；或者使用带通配符的KMP。