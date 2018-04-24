<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
程序结构
======

🌟如果发现有不太理解的点的话，**点击蓝色的小标题或文中链接**可以跳转到教程原文哦~🌟

新来的用户可以登录一下，这样就可以记录学习状态啦~

输出、注释和转义
------

### [输出（点像我这样的蓝色字可以跳到教程原文）](https://coderecipe.cn/learn/2#section-%E8%BE%93%E5%85%A5%E8%BE%93%E5%87%BA)
AP只需要我们知道两种输出，一种是`System.out.print`一种是`System.out.println`，区别在于前者不会换行，后者会。AP输入不要求掌握，出现输入的话会专门说明。

可以参考如下例子：
#### `System.out.println：`
<lab lang="java" parameters="filename=Hello.java">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)查看。</notice>
public class Hello {
  public static void main(String[] args) {
      System.out.println("第一行输出");
      System.out.println("第二行输出");
  }
}
</lab>

#### `System.out.print：`
<lab lang="java" parameters="filename=Hello.java">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)查看。</notice>
public class Hello {
  public static void main(String[] args) {
      System.out.print("第一行输出");
      System.out.println("还是第一行输出");
  }
}
</lab>

### [注释](https://coderecipe.cn/learn/2#section-%E6%B3%A8%E9%87%8A)
除了Javadoc，注释本身Java来说并没有什么含义，然而对阅读代码的人来说却至关重要。注释描述了代码的内容和要注意的点。注释有两种，一种是行注释，就像上面的这个例子，只对一行`//`后面的内容有效，另一种是块注释，写法是`/*注释内容*/`对`/*`和`*/`之间的内容都有效，可以好几行。

[Javadoc](https://coderecipe.cn/learn/3?chapter=1#section-javadoc%E6%B3%A8%E9%87%8A)是一种特殊的注释，描述函数的运行环境和效果。

### [转义](https://coderecipe.cn/learn/2#section-%E8%BD%AC%E4%B9%89)
AP中需要掌握以下的[转义序列(escape sequence)](https://coderecipe.cn/learn/2#section-%E8%BD%AC%E4%B9%89):
| 序列 | 含义 |
| - | - |
| `\"` | 双引号 |
| `\n` | 换行 |
| `\\` | `\`本身 |

[变量和类型（点像我这样的蓝色字可以跳到教程原文）](https://coderecipe.cn/learn/2?chapter=1)
------

### [变量](https://coderecipe.cn/learn/2?chapter=1#section-%E5%8F%98%E9%87%8F%E7%9A%84%E5%AE%9A%E4%B9%89%E3%80%81%E8%B5%8B%E5%80%BC%E5%92%8C%E8%AF%BB%E5%8F%96)
[变量](https://coderecipe.cn/learn/2?chapter=1#section-%E5%8F%98%E9%87%8F%E7%9A%84%E5%AE%9A%E4%B9%89%E3%80%81%E8%B5%8B%E5%80%BC%E5%92%8C%E8%AF%BB%E5%8F%96)(variable)的定义(define)方式和初始化(initialize)方式：
```java
变量类型 变量名 = 初始化值;
```
例如：
```java
String text = "Hello Java!";
```

### [变量命名](https://coderecipe.cn/learn/2?chapter=1#section-%E7%BB%99%E5%8F%98%E9%87%8F%E8%B5%B7%E5%90%8D%E5%AD%97)
AP中我们需要知道这4条命名规则：
1. 变量名称需要有描述性，比如（`string`这种变量名就没有准确描述存储的内容）
2. 如果要描述内容的名称只有一个单词，那么这个变量名可以用这个单词的全小写形式（如`number`），如果名称由两个或两个以上个单词组成，那么变量名为第一个单词首字母小写，剩下的单词紧跟着第一个单词，但第一个字母大写（如学生数量为`studentNumber`）
3. 在变量名中，第一个位置不能是数字（如不能以`1Hello`作为变量名），同时变量名不能有空格，不能有“-”、“/”等对计算机来说有歧义的符号（如`abc*def`会被计算机理解成abc乘以def）
4. 在Java中，变量不能是系统保留用的关键字（比如`class`、`static`）

### [类型和储存方式](https://coderecipe.cn/learn/2?chapter=1#section-%E7%B1%BB%E5%9E%8B%E5%8F%8A%E5%82%A8%E5%AD%98%E6%96%B9%E5%BC%8F)
**最基本**的几个类型：
1. 整数类型`int`，在计算机中，`int`是以二进制形式储存的，可以存储`-2^31`到`2^31-1`之间的数。
2. 浮点类型`double`，对应我们一般称的“小数”，同样也是通过二进制储存的，使用科学计数法，存储方式为：`符号 * 有效位数 * 2 ^ 指数`，还可以表示数字无效（`NaN`, Not a Number），或者正负无穷（`Infinity`和`-Infinity`）。
3. 字符串类型`String`，字符串类型储存的是一串文字。字符串的储存方式是把每个字符通过一张叫ASCII码表的转换表对应成数字，再把数字一个一个地按顺序储存起来。
4. 布尔类型`boolean`，只有两种取值，一种是真（`true`），一种是假（`false`）。
5. 数组和数组列表`Array`和`ArrayList`，本教程之后会说明，也可以看[Array和ArrayList教程](https://coderecipe.cn/learn/4)。

### [`final`变量](https://coderecipe.cn/learn/2?chapter=1#section-final%E5%8F%98%E9%87%8F)
`final`变量（final variable， 也叫用户定义常量，即user-defined constant），是只能赋值一次的特殊变量。

[运算和操作符](https://coderecipe.cn/learn/2?chapter=1#section-%E8%BF%90%E7%AE%97%E5%92%8C%E6%93%8D%E4%BD%9C%E7%AC%A6)
------
### 数学运算
加减乘除和除余基本运算（不包括乘方运算），分为整数运算和浮点运算两种，进行哪种看的是操作数有没有浮点值。

要点：
1. 整数运算的结果一定是整数，可以理解为算数除法舍去小数点后的部分的结果。浮点运算可能会有精度问题，不能直接判断相等
2. 除零的情况下整数运算和浮点运算的不同，整数会抛出异常，浮点则返回`NaN`

### 类型转换（cast）
在整型前面加上`(double)`，转为浮点类型。在浮点前面加上`(int)`可以转为整型，不过要小心丢失小数点后面的内容。

### 关系运算
主要有：

| 运算符 | 含义 |
| - | - |
| `>` | 大于 |
| `<` | 小于 |
| `>=` | 大于等于 |
| `<=` | 小于等于 |
| `==` | 是否等于 |
| `!=` | 是否不等于 |

关系运算符返回一个布尔类型的数值，如果关系是正确的，那么返回真（`true`），如果关系是错误的，那么返回假（`false`）。

### 逻辑运算

关系运算判断的是布尔值本身或者布尔值之间的关系，主要有：

| 运算符 | 含义 |
| - | - |
| && | 与 |
| &#124;&#124; | 或 |
| ! | 非 |

与需要左右两边都为真才返回真，或只需要一边为真即可，非只需要右边的一个操作数，会反过来输出（操作数为真输出假，操作数为假输出真）。

### 赋值运算和增减量运算

赋值运算符由最基本的`=`运算符和复合赋值运算符组成：

| 运算符 | 含义 |
| - | - |
| `=` | 赋值 |
| `+=` | 加上 |
| `-=` | 减去 |
| `*=` | 乘上 |
| `/=` | 除去 |
| `%=` | 进行除余赋值运算 |
| `++` | 增量运算，与`+=1`等价 |
| `--` | 减量运算，与`-=1`等价 |

一个复合运算符可以看成算术运算符加上赋值运算符。

### 优先级
Java中运算优先级如下，从高往低排列：
```
a) ()
b) ! , ++ , -
c) * , / , %
d) + , -
e) < , > , <= , >=
f) == , !=
g) &&
h) ||
i) = , += , -= *= , /= , %=
```

[判断结构](https://coderecipe.cn/learn/2?chapter=2)
------
### [if...else if...else结构](https://coderecipe.cn/learn/2?chapter=2#section-%E5%A6%82%E6%9E%9C%E2%80%A6%E5%90%A6%E5%88%99%E5%A6%82%E6%9E%9C%E2%80%A6%E5%90%A6%E5%88%99%E2%80%A6)
```java
if (条件1) {
···
//如果条件1为真，则执行，执行完跳出if
} else if(条件2) { //条件1为假才判断
//如果条件2为真，则执行，执行完跳出if
// 这里还可以加其他的else if
} else { // 前面的条件都不对才判断
···
//如果条件为假，则执行
}
```

### [最小化求值/短路求值原理（short-circuit evaluation）](https://coderecipe.cn/learn/2?chapter=2#section-%E6%9C%80%E5%B0%8F%E5%8C%96%E6%B1%82%E5%80%BC%E5%8E%9F%E7%90%86)
计算机程序再运行的时候会自动排除一些不可能发生的情况，从而让电脑少算一些值来加快电脑运行的速度。

### [德摩根定律](https://coderecipe.cn/learn/2?chapter=2#section-%E5%BE%B7%E6%91%A9%E6%A0%B9%E5%AE%9A%E5%BE%8B)

在计算机里，德摩根定律表示的是两种等价关系：
* `!a && !b <=> !(a || b)`
* `!a || !b <=> !(a && b)`
其中，`<=>`意味着等价，前提条件是`a`和`b`都是布尔值。

[循环结构](https://coderecipe.cn/learn/2?chapter=3)
------

### [for循环](https://coderecipe.cn/learn/2?chapter=3#section-for%E5%BE%AA%E7%8E%AF)

for循环的用法如下：
```java
for(初始条件;终止条件;更新语句){
  ...//循环内容
}
```
for的运行方式是：

a)先运行初始条件，然后测试终止条件，如果终止条件不符合（false）则跳出循环继续执行;

b)如果终止条件符合（true）则继续运行，执行循环内容，然后运行更新语句;

c)重复执行b)直到循环结束。

### [while循环](https://coderecipe.cn/learn/2?chapter=3#section-while%E5%BE%AA%E7%8E%AF)

while循环的运行原理和for循环大抵相同，但在写法上有一定差异。while循环的写法如下：
```java
while(测试条件){
  ...//循环内容
}
```
while循环会先判断条件，如果符合（true）就会继续执行循环内容，不符合就会跳出循环执行下面的内容，执行完循环内容后会返回来判断条件，如果符合的话接着执行循环内容，一直重复知道条件不符合（false）为止。

### [for-each循环](https://coderecipe.cn/learn/2?chapter=3#section-for-each%E5%BE%AA%E7%8E%AF)

这种代码用于循环访问一个数组或者集合中的所有元素。用法如下：
```java
for(SomeType element : collection){
  ...//循环内容
}
```
注意： for-each 循环不能被用来替换或删除元素，同时不显示index。

`break`的作用是跳出当前循环块（for、while、for-each）或程序块（switch）并执行循环块或程序块外的代码。

`continue`用于结束循环体中其后语句的执行，并跳回循环程序块的开头执行下一次循环，而不是立刻循环体。

[异常（exception）](https://coderecipe.cn/learn/2?chapter=5)
------
**异常**（exception）是一种Java程序在执行过程中抛出的错误情况。需要掌握的有：
```java
ArithmeticException（算术错误如0/0）
NullPointerException（访问了空引用）
IndexOutOfBoundsException（在List越界抛出）
ArrayIndexOutOfBoundsException（是IndexOutOfBoundsException的子类，数组越界抛出）
IllegalArgumentException（参数错误）
```

