<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/6)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
面向对象编程
======

🌟如果发现有不太理解的点的话，**点击蓝色的小标题或文中链接**可以跳转到教程原文哦~🌟

类、对象、属性和方法
------

### [类（class）、对象（object）、属性（property）和方法（method）](https://coderecipe.cn/learn/3/0)
AP中我们需要掌握[类](https://coderecipe.cn/learn/3/0#section-%E4%BB%80%E4%B9%88%E6%98%AF%E7%B1%BB)、[对象](https://coderecipe.cn/learn/3/0#section-%E5%AF%B9%E8%B1%A1%E5%92%8C%E5%AF%B9%E8%B1%A1%E7%B1%BB%E5%9E%8B)、[属性和方法](https://coderecipe.cn/learn/3/0#section-%E5%B1%9E%E6%80%A7%E5%92%8C%E6%96%B9%E6%B3%95)三者的概念与运用。类是一个模板，它描述一类对象的行为和状态。对象的状态就是属性，而方法就是对象行为的体现。方法操作对象内部状态的改变，对象的相互调用也是通过方法来完成。

我们还可以用过参数来告诉这个函数具体的内容，比如setSpeed(double newSpeed)这个函数就可以让我们给一个浮点参数newSpeed，让我们告诉它要设定的车的具体速度，这里的newSpeed写在函数定义里，称为形式参数（parameter），形式参数一定是要是一个合法的变量名，参数与参数用逗号隔开，每一个参数前面都需要有一个参数类型。

Java的方法以如下格式呈现：
```java
public/private + 可能有 static 关键字 + 返回值类型 + 方法名(形式参数列表){
  方法体
}
```

### [作用域](https://coderecipe.cn/learn/3#section-作用域和三个关键字)
作用域其实就是访问范围。在函数内定义的变量，作用域是在变量定义后到函数结束。在更内部（比如for循环的初始化内）定义的变量，作用域就仅限于那一个部分，到大括号结束为止。

`public`关键字说明的是这个变量或者方法在类外是可见的，不仅可以在类本身里面调用，而且可以在类外通过.运算符调用。`private`修饰符所修饰的方法、属性仅能在本类中使用。

`static`关键字定义的方法被称为静态方法（static method）实际上也被称为类方法（class method）。相反，不带有`static`方法的就被称为实例方法（instance method）了。静态方法并不随着我们的对象的创建才能使用，静态方法是与对象无关的。静态方法能够直接通过类的调用来使用。换句话说，实例方法是面向实例，也就是对象的（对象就是类的实例），而静态方法是面向类的。

`this`这个关键字代表的就是对象中的成员变量或者方法。也就是说，如果在某个变量前面加上一个this关键字，其指的就是这个对象的成员变量或者方法，而不是指成员方法的形式参数或者局部变量。

### [构造方法](https://coderecipe.cn/learn/3/1#section-构造方法)

每个类都有构造方法。如果没有专门为类定义构造方法，Java编译器将会为该类提供一个默认构造方法。在创建一个对象的时候，至少要调用一个构造方法。构造方法是没有返回值的，并且构造方法的名称必须与类名相同，一个类可以有多个构造方法。

例如：
```java
public Dog(String name, String sex, int age){
    System.out.println("My name is " + name + 
        ", and my sex is " + sex + ". I'm " + 
        age + " years old.");
}
```
就是`Dog`类的构造方法。

### [访问器和更改器](https://coderecipe.cn/learn/3/1#section-访问器和更改器)

习惯上，我们使用getter与setter方法来访问与修改Java属性值。这两种方法分别叫“访问器（Accessor）”与“更改器(Mutator)”

### [方法重载](https://coderecipe.cn/learn/3/1#section-方法重载)
方法重载指的是，多个方法有同样的名字，却有不同的传入参数列表。

引用
------

### [原始类型和引用类型](https://coderecipe.cn/learn/3/2#section-原始类型和引用类型)
在Java里面的类型有分两种，原始类型（primitive types）和引用类型（reference types）。Java自带的类型中，凡是首字母为小写的都是原始类型（如int，bool，double），凡是首字母为大写的都是引用类型（如String，Object），自己定义的类的类型（比如之前说的Car）也都是引用类型。

这两种类型的主要区别在于储存方式。原始类型的数据是直接储存的，而引用类型是按引用（reference）储存，就是变量只是记下了这个对象真正的位置，而并不是储存了整个对象。

### [空引用](https://coderecipe.cn/learn/3/2#section-空引用)
空引用指的是，引用的对象没有被初始化（initialize），也就是没有被赋值。

继承和多态
------
### [继承](https://coderecipe.cn/learn/3/3)
继承说的是，"子类"可以继承"父类"的属性，或者是方法。一个由其他的类派生出来的类，叫做子类(subclass)，而派生出子类的类，则叫做父类（superclass或parent class)。子类包含着父类的所有属性和方法，同时，子类还可以具有自己独有的属性和方法，因此，子类可以包含着比父类更多的属性和方法！

假如有两个类，A与B，而A派生出B，换句话说，B继承自A，则：
```java
class A{
//类的内容
}

class B extends A{
//类的内容
}
```

### [instanceof关键字](https://coderecipe.cn/learn/3/3#section-实现继承)
我们可以通过instanceof关键字判断父类与子类是否存在继承的关系。instanceof 是 Java 的保留关键字，它的作用是测试它左边的对象是否是它右边的类的实例，或左边的类是否由继承自右边的类。用来判断哺乳动物是否是动物，狗是否是动物等，如果是那么就是真，否则就是假，instanceof关键字返回 boolean 的数据类型。
例如：
```java
public class Vehicle {   

}  

public class Bicycle extends Vehicle{
    public static void main(String[] args) {
        system.out.println(Bicycle instanceof      Vehicle); // 输出结果为：ture  

    }  
}
```

### [方法重写](https://coderecipe.cn/learn/3/3#section-方法重写)
方法重写(Method override)指的是，如果一个类继承了其父类的方法，那么我们可以通过方法重写，用同名的方法，来"覆盖"掉所继承的父类的对应方法。相当于，在子类中我们"重新写了"一次，父类中该名称的方法，并用此方法来替代所继承的同名方法。

### [抽象类](https://coderecipe.cn/learn/3/3#section-抽象类)
"抽象"这一概念的引入，是面向对象编程的一个重要思想：从高层次的抽象、模糊概念开始，逐步细化化。也就是由抽象到具体，由概念到实现，首先关注的是解决一个问题的总体概念，再逐步逐步把这个总体概念拆分、细化、具体落实下去。

我们可以用"abstract"这个关键字对一个类进行修饰，把这个类定义成抽象的类。同样，我们也可以用"abstract"这个关键字对一个方法进行修饰，把这个方法定义成抽象方法。如：
```java
public abstract class Animal{
    public abstract void eat();
    public abstract void roam();
}
```

### [多态（polymorphism）](https://coderecipe.cn/learn/3/4#section-初识多态)
在Java中，方法调用总是由调用这一方法的对象实际指向的对象类型（也就是在new语句后紧跟着的类型），而不是由这一对象引用的对象类型（也就是在new语句中，实际对象前面的那个类型）来决定的。

例如，在语句`Animal puppy = new Dog();`中，实例对象puppy所引用的类型是Animal，而其实际指向的类型则是Dog。这个机制就叫做多态。  

### [向下转型（down casting）](https://coderecipe.cn/learn/3/4#section-类型转换)
把一个子类引用指向父类对象的转型过程，称作向下转型。

在下面这个例子里，我们假设getID()方法是GradStudent类中特有的一个public实例方法，没有在Student类中被定义，GradStudent类继承自Student类。

```java
Student student = new GradStudent();
GradStudent gradstudent = new GradStudent();
int x = ((GradStudent) student).getID(); //这里用到了向下转型
```

### [动态绑定（dynamic bonding)](https://coderecipe.cn/learn/3/4#section-动态绑定)
动态绑定，指的是，当存在方法重写时，关于调用哪一个实例方法的决定，是在Java程序运行时(run-time)（Java虚拟机JVM实时解析运行Java字节码时）才实时作出的。

### [使用`super`调用父类方法](https://coderecipe.cn/learn/3/4#section-使用“super”调用父类)
如果在子类中，我们对一个方法进行了重写，则重写过的方法默认覆盖过了父类中的同名方法，但若我们就是想使用父类中的，被重写过的，那一个原本的方法，那我们就可以通过使用关键字super来调用被重写过(overridden)的方法。

比方说：
```java
public class Superclass {
    public void printMethod() {
        System.out.println("Printed in Superclass.");
    }
}

public class Subclass extends Superclass {
    // overrides printMethod in Superclass
    public void printMethod() {
        super.printMethod();
        System.out.println("Printed in Subclass.");
    }
    public static void main(String[] args) {
        Subclass s = new Subclass();
        s.printMethod();    
    }
}
```

上述代码的运行结果为：
```java
Printed in Superclass.
Printed in Subclass.
```

### [`super`与构造方法](https://coderecipe.cn/learn/3/4#section-“super”与构造方法)
在子类中使用super调用父类中的构造方法的语法是`super()`或`super(parameter1, parameter2, ...)`
若使用`super()`, 父类中不带传入参数列表的构造方法将会被调用。当使用带传入参数的 super关键字，则父类中具有匹配的传入参数列表的构造函数将会被调用。

[接口](https://coderecipe.cn/learn/3/5)
------
在Java编程语言中，接口（interface）是一个引用类型，类似于一个类，它相当于是一类方法的集合（有点像抽象类）。在接口中，这些方法，就如同抽象类一样，可以是抽象的（只包含一个声明，却不包括具体实现），也可以是普通的实例方法或静态方法（包括具体方法的实现）。 也就是说，对于接口，方法体只存在于普通的实例方法或静态方法中。 接口不能被实例化 - 它们只能由类实现或由其他接口扩展。

### [实现（implement）接口](https://coderecipe.cn/learn/3/5#section-实现接口)
我们可以使用`implement`关键字让类去使用已经定义好的接口。例如：
```java
public class Fish implements SwimmingObject{
//类的内容
}
```
