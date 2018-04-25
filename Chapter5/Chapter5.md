<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
程序的构建
======

🌟如果发现有不太理解的点的话，**点击蓝色的小标题或文中链接**可以跳转到教程原文哦~🌟

[程序的实现方法](https://coderecipe.cn/learn/3/8)
------
设计一个成功的程序需要大量的步骤，而我们需要掌握一些科学、高效的程序设计方式，来实现我们的目的。在AP考试中，我们需要掌握[瀑布模型](https://coderecipe.cn/learn/3/8#section-瀑布模型)以及[面向对象程序设计](https://coderecipe.cn/learn/3/8#section-面向对象程序设计)。

[测试调试](https://coderecipe.cn/learn/3/8)
------
在AP CS A中，我们需要掌握两种测试和调试的方法。

### 测试数据的选择
测试数据要尽可能多样，不仅仅是在输入范围内的，还要有范围外的。比如一个平方根函数，不仅仅是正数，我们可以给它传入一个负数作为参数测试它输出的是不是我们预测的结果（比如`-1`的平方根应该是`NaN`）。

### 输出语句调试方法
我们可以在执行的语句里面加入`System.out.println`语句来帮助我们调试，比如我们想知道以下这个循环里面每次循环i的数值，就可以使用这个方法调试，然后在调试完成之后或者程序上线的时候把这些调试代码注释掉或者去掉即可：

<lab lang="java" parameters="filename=Hello.java">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)查看。</notice>
public class Hello {
  public static void main(String[] args) {
      int i = 1;
      int j = 0;
      while(i<986){
          System.out.println("i="+i+", j="+j);
          j++;
          i *= 2;
      }
  }
}
</lab>