---
aliases: 
tags:
  - 编程语言
  - Java
  - 概念解释
  - 关键字
---
指向、调用、参数、返回值
对象、方法、构造函数（有参、无参）
# This

1. 指向当前对象

也就是当前类为模板new出来的对象，this.xxx就指向实例变量，而不是构造方法的参数，因为相当于调用了对象的xxx。

2. 调用当前类的方法

在同一个类下，可以用this调用当前类的方法，直接写方法名编译器会隐式加上this.methodName。

3. 调用当前类的构造方法

在无参构造函数下第一行放置this(参数);可以调用当前类下的有参构造函数；
在有参构造函数下第一行放置this();可以调用当前类下的无参构造函数；

4. 作为参数在方法中传递

此时this指向当前类的对象。

5. 作为参数在构造方法中传递

此时this指向当前类的对象，当我们需要在多个类中使用一个对象的时候，这非常有用

6. 作为方法的返回值

this作为方法的返回值，指向对象自身，从而实现连续的方法调用，也就是[[知识库/卡片/Java/链式调用]]。

# super

1. 子类方法重写时访问到父类的方法
2. 子类构造方法的第一行如果是super()，就是用来调用父类的无参构造方法
3. 当子类第一行是super且含参，则是用来调用父类的有参构造方法，可以提高代码的可重用性。（参数之间逗号分隔）
