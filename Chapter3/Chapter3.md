<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
标准类
======

🌟如果发现有不太理解的点的话，**点击蓝色的小标题或文中链接**可以跳转到教程原文哦~🌟

[数学类](https://coderecipe.cn/learn/2/4)
------

为了方便我们在Java中使用数学方法和常量，Java专门开发了java.math类。如果我们需要，可以直接调取。常数主要有e和圆周率PI两个，调用方法如下：

```java
Math.PI;
Math.E;
```

通过java.math类，我们也可以生成随机数。生成随机数的方法如下：

```java
math.random();
```

这样可以随机生成一个0到1之间的double类型的数。如果你觉得0到1这个范围不符合你的要求，也可以使用数学方法去调整。比如这样：

```java
math.random() * 10; //大于0小于10的随机数
math.random() + 1; //大于1小于2的随机数
```

可以参考如下例子：
<lab lang="java" parameters="filename=test.java">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)查看。</notice>
public class test {
   public static void main(`String`[] args) { 
     System.out.println(Math.PI);
     System.out.println(Math.E);
     System.out.println(math.random())
   }
}
</lab>

[`Object`类](https://coderecipe.cn/learn/3/6)
------

我们在继承章节中讲过，在Java中，除了最终超类：`Object`类，所有的类都有且仅有一个直接的父类（这被称为单继承）。当没有明确在程序中声明某些类所属的父类时，这些类都是最终超类：`Object`类的（隐式）子类。

那么，`Object`类，就是Java世界中，处在类继承层次结构上的最高层次的那一个类，也叫作最终超类(ultimate superclass)。`Object`类是一个普通的类，而非抽象类。

在Java中，所有的类都被规定为继承自`Object`类，也就是说，`Object`类是所有类的直接或间接父类。

在AP考试中，我们需要掌握两个`Object`类中的内置方法：`toString()`方法，以及`equals()`方法。

`toString()`方法的具体实现语句如下：
```java
public String toString()
```
这是一个public的，返回值为`String`型的方法。

`equals()`这个方法用于判断两个对象在实际意义上（也就是对象所包含的值）是否真的相等，可以参考 [`equals()`方法](https://coderecipe.cn/learn/3/6#section-`Object`类里的方法)。

[`String`类](https://coderecipe.cn/learn/3/7)
------
`String`是Java中特殊的一种类，它是一种引用类型，而不是原始数据类型（注意`String`类是大写字母开头的）。`String`类型的对象是字符串，也就是一系列的字符。所有`String`类型的变量, 例如`"Hello World!"`，都作为实例变量成为类的一个实例对象，这样的变量，称作字面量(literal)。一个`String`类型的字面量，包含着零个（包括0）以上的字符，字符的涵义包括双引号" "中的所有字符，包括空格与转义符。（双引号本身不属于字面量的一部分）。如下几个例子都是合法的字面量。

```java
"" //这是一个空的字面量
"2468"
"I must\n go home"
```

在AP考试中，我们需要了解 [`String`对象的创建和更新](https://coderecipe.cn/learn/3/7#section-string%E5%AF%B9%E8%B1%A1%E7%9A%84%E5%88%9B%E5%BB%BA%E5%92%8C%E6%9B%B4%E6%96%B0)、[`String`类的方法](https://coderecipe.cn/learn/3/7#section-string%E7%B1%BB%E7%9A%84%E6%96%B9%E6%B3%95)、[`String`类的比较](https://coderecipe.cn/learn/3/7#section-string%E7%B1%BB%E7%9A%84%E6%AF%94%E8%BE%83)。