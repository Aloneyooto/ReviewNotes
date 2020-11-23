[TOC]

# Java基础

## 基础知识

### JDK，JRE， JVM

（JVM需要补充）
-   JDK：Java Development Kit 的简称，java 开发工具包，提供了 java 的**开发环境和运行环境**。
-   JRE：Java Runtime Environment 的简称，java **运行环境**

### java 中的 Math.round(-1.5) 等于多少？

等于 -1，因为在数轴上取值时，中间值（0.5）向右取整，所以正 0.5 是往上取整，负 0.5 是直接舍弃。

### 数据类型

| 基本类型 | 位数 | 字节 |
| -------- | ---- | ---- |
| int      | 32   | 4    |
| short    | 16   | 2    |
| long     | 64   | 8    |
| byte     | 8    | 1    |
| char     | 16   | 2    |
| float    | 32   | 4    |
| double   | 64   | 8    |
| boolean  | ？   | ？   |

### final, finally, finalize 的区别

- final 用于修饰属性,方法和类, 分别表示属性不能被重新赋值, 方法不可被覆盖, 类不可被继承.

- finally 是**异常处理语句结构**的一部分，一般以try-catch-finally出现，finally代码块表示总是被执行.

- finalize 是**Object类**的一个方法，该方法一般由**垃圾回收器**来调用，当我们调用System.gc() 方法的时候，由垃圾回收器调用finalize()方法，回收垃圾，JVM并不保证此方法总被调用.

### 类的实例化顺序

父类静态代码块/静态域->子类静态代码块/静态域 -> 父类非静态代码块 -> 父类构造器 -> 子类非静态代码块 -> 子类构造器

### Java创建对象的5种方式

- 用new语句创建对象。

- 使用反射，使用`Class.newInstance()`创建对象/调用类对象的**构造方法**——Constructor

- 调用对象的`clone()`方法。

- 运用反序列化手段，调用`java.io.ObjectInputStream`对象的`readObject()`方法.

- 使用Unsafe

### 面向对象的特征（没写完）

三大特征：

- 封装
- 继承
- 多态

### 多态的实现原理

- 多态机制包括静态多态（编译时多态）和动态多态（运行时多态）

- 静态多态比如说**重载**，动态多态一般指**在运行时才能确定调用哪个方法**，我们通常所说的多态一般指运行时多态

- 多态核心之处就在于对**父类方法的改写**或**对接口方法的实现**，以取得在运行时不同的执行效果。

- Java 里对象方法的调用是依靠类信息里的方法表实现的，当调用对象的某个方法时，JVM查找该对象类的方法表以确定该方法的直接引用地址，有了地址后才真正调用该方法。

### 抽象类与接口

#### 抽象类和接口的对比

-   抽象类是用来捕捉子类的通用特性的。接口是抽象方法的集合。
    
-   从设计层面来说，抽象类是对类的抽象，是一种模板设计，接口是行为的抽象，是一种行为的规范。
    

**相同点**

-   接口和抽象类都不能实例化
-   都位于继承的顶端，用于被其他实现或继承
-   都包含抽象方法，其子类都必须覆写这些抽象方法

**不同点**

- 声明:抽象类使用abstract关键字声明,接口使用interface关键字声明
- 实现:子类使用extends关键字来继承抽象类。如果子类不是抽象类的话，它需要提供抽象类中所有声明的方法的实现;子类使用implements关键字来实现接口。它需要提供接口中所有声明的方法的实现
- 构造器:抽象类可以有构造器;接口不能有构造器
- 访问修饰符:抽象类中的方法可以是任意访问修饰符;接口方法默认修饰符是public。并且不允许定义为 private 或者 protected
- 继承:一个类最多只能继承一个抽象类;一个类可以实现多个接口
- 字段声明:抽象类的字段声明可以是任意的;接口的字段默认都是 static 和 final 的

**备注**：Java8中接口中引入默认方法和静态方法，以此来减少抽象类和接口之间的差异。

`现在，我们可以为接口提供默认实现的方法了，并且不用强制子类来实现它。`

-   接口和抽象类各有优缺点，在接口和抽象类的选择上，必须遵守这样一个原则：
    -   行为模型应该总是通过接口而不是抽象类定义，所以通常是优先选用接口，尽量少用抽象类。
    -   选择抽象类的时候通常是如下情况：需要定义子类的行为，又要为子类提供通用的功能。

#### 普通类和抽象类有哪些区别？

-   普通类不能包含抽象方法，抽象类可以包含抽象方法。
-   抽象类不能直接实例化，普通类可以直接实例化。

#### 抽象类能使用 final 修饰吗？

-   不能，定义抽象类就是让其他类继承的，如果定义为 final 该类就不能被继承，这样彼此就会产生矛盾，所以 final 不能修饰抽象类

#### 抽象类必须要有抽象方法吗？

不需要，抽象类不一定非要有抽象方法。

```
abstract class Cat {
    public static void sayHi() {
        System.out.println("hi~");
    }
}
```

#### 创建一个对象用什么关键字？对象实例与对象引用有何不同？

-   new关键字，new创建对象实例（对象实例在堆内存中），对象引用指向对象实例（对象引用存放在栈内存中）。一个对象引用可以指向0个或1个对象（一根绳子可以不系气球，也可以系一个气球）;一个对象可以有n个引用指向它（可以用n条绳子系住一个气球）

### 内部类

#### 什么是内部类？

-   在Java中，可以将一个类的定义放在另外一个类的定义内部，这就是**内部类**。内部类本身就是类的一个属性，与其他属性定义方式一致。

#### 内部类的分类有哪些

`内部类可以分为四种：**成员内部类、局部内部类、匿名内部类和静态内部类**。`

##### 静态内部类

-   定义在类内部的静态类，就是静态内部类。
    
    ```
    public class Outer {
    
        private static int radius = 1;
    
        static class StaticInner {
            public void visit() {
                System.out.println("visit outer static  variable:" + radius);
            }
        }
    }
    
    ```
    
-   静态内部类**可以访问外部类所有的静态变量，而不可访问外部类的非静态变量**；静态内部类的创建方式，`new 外部类.静态内部类()`，如下：
    
    ```
    Outer.StaticInner inner = new Outer.StaticInner();
    inner.visit();
    
    ```
    

##### 成员内部类

-   定义在类内部，成员位置上的非静态类，就是成员内部类。
    
    ```
    public class Outer {
    
        private static  int radius = 1;
        private int count =2;
        
         class Inner {
            public void visit() {
                System.out.println("visit outer static  variable:" + radius);
                System.out.println("visit outer   variable:" + count);
            }
        }
    }
    
    ```
    
-   **成员内部类可以访问外部类所有的变量和方法，包括静态和非静态，私有和公有。**成员内部类依赖于外部类的实例，它的创建方式`外部类实例.new 内部类()`，如下：
    
    ```
    Outer outer = new Outer();
    Outer.Inner inner = outer.new Inner();
    inner.visit();
    
    ```
    

##### 局部内部类

-   定义在**方法中**的内部类，就是局部内部类。
    
    ```
    public class Outer {
    
        private  int out_a = 1;
        private static int STATIC_b = 2;
    
        public void testFunctionClass(){
            int inner_c =3;
            class Inner {
                private void fun(){
                    System.out.println(out_a);
                    System.out.println(STATIC_b);
                    System.out.println(inner_c);
                }
            }
            Inner  inner = new Inner();
            inner.fun();
        }
        public static void testStaticFunctionClass(){
            int d =3;
            class Inner {
                private void fun(){
                    // System.out.println(out_a); 编译错误，定义在静态方法中的局部类不可以访问外部类的实例变量
                    System.out.println(STATIC_b);
                    System.out.println(d);
                }
            }
            Inner  inner = new Inner();
            inner.fun();
        }
    }
    
    ```
    
-   定义在**实例方法**中的局部类可以访问**外部类的所有变量和方法**，定义在**静态方法**中的局部类只能访问**外部类的静态变量和方法**。局部内部类的创建方式，在对应方法内，`new 内部类()`，如下：
    
    ```
    public static void testStaticFunctionClass(){
        class Inner {
        }
        Inner  inner = new Inner();
     }
    
    ```
    

##### 匿名内部类

-   匿名内部类就是没有名字的内部类，日常开发中使用的比较多。
    
    ```
    public class Outer {
    
        private void test(final int i) {
            new Service() {
                public void method() {
                    for (int j = 0; j < i; j++) {
                        System.out.println("匿名内部类" );
                    }
                }
            }.method();
        }
     }
     //匿名内部类必须继承或实现一个已有的接口 
     interface Service{
        void method();
    }
    
    ```
    
-   除了没有名字，匿名内部类还有以下特点：
    
    -   匿名内部类必须继承一个抽象类或者实现一个接口。
    -   匿名内部类不能定义任何静态成员和静态方法。
    -   当所在的方法的形参需要被匿名内部类使用时，必须声明为 final。
    -   匿名内部类不能是抽象的，它必须要实现继承的类或者实现的接口的所有抽象方法。
-   匿名内部类创建方式：
    
    ```
    new 类/接口{ 
      //匿名内部类实现部分
    }
    
    ```
    

#### 内部类的优点

`我们为什么要使用内部类呢？因为它有以下优点：`

-   一个内部类对象可以访问创建它的外部类对象的内容，包括私有数据！
-   内部类不为同一包的其他类所见，具有很好的封装性；
-   内部类有效实现了“多重继承”，优化 java 单继承的缺陷。
-   匿名内部类可以很方便的定义回调。

#### 内部类有哪些应用场景

1.  一些多算法场合
2.  解决一些非面向对象的语句块。
3.  适当使用内部类，使得代码更加灵活和富有扩展性。
4.  当某个类除了它的外部类，不再被其他的类使用时。

#### 局部内部类和匿名内部类访问局部变量的时候，为什么变量必须要加上final？

-   局部内部类和匿名内部类访问局部变量的时候，为什么变量必须要加上final呢？它内部原理是什么呢？先看这段代码：
    
    ```
    public class Outer {
    
        void outMethod(){
            final int a =10;
            class Inner {
                void innerMethod(){
                    System.out.println(a);
                }
            }
        }
    }
    
    ```
    
-   以上例子，为什么要加final呢？是因为**生命周期不一致**， 局部变量直接存储在栈中，当方法执行结束后，非final的局部变量就被销毁。而局部内部类对局部变量的引用依然存在，如果局部内部类要调用局部变量时，就会出错。加了final，可以确保局部内部类使用的变量与外层的局部变量区分开，解决了这个问题。
    

#### 内部类相关，看程序说出运行结果

```
public class Outer {
    private int age = 12;

    class Inner {
        private int age = 13;
        public void print() {
            int age = 14;
            System.out.println("局部变量：" + age);
            System.out.println("内部类变量：" + this.age);
            System.out.println("外部类变量：" + Outer.this.age);
        }
    }

    public static void main(String[] args) {
        Outer.Inner in = new Outer().new Inner();
        in.print();
    }

}

```

运行结果：

```
局部变量：14
内部类变量：13
外部类变量：12
```

### 重写与重载

#### 构造器（constructor）是否可被重写（override）

-   构造器不能被继承，因此不能被重写，但可以被重载。

#### 重载（Overload）和重写（Override）的区别。重载的方法能否根据返回类型进行区分？

-   方法的重载和重写都是实现多态的方式，区别在于**前者实现的是编译时的多态性**，而**后者实现的是运行时的多态性**。
    
-   重载：发生在**同一个类**中，**方法名相同**，**参数列表不同（参数类型不同、个数不同、顺序不同）**，与方法返回值和访问修饰符无关，即重载的方法不能根据返回类型进行区分
    
-   重写：发生在**父子类**中，方法名、**参数列表必须相同**，**返回值小于等于父类**，**抛出的异常小于等于父类**，**访问修饰符大于等于父类**（里氏代换原则）；如果父类方法访问修饰符为private则子类中就不是重写。

### 对象相等的判断

#### == 和 equals 的区别是什么

-   **==**  : 它的作用是判断两个对象的地址是不是相等。即，判断两个对象是不是同一个对象。(基本数据类型 == 比较的是值，引用数据类型 == 比较的是内存地址)
    
-   **equals()**  : 它的作用也是判断两个对象是否相等。但它一般有两种使用情况：
    
    -   情况1：类没有覆盖 equals() 方法。则通过 equals() 比较该类的两个对象时，等价于通过“==”比较这两个对象。
        
    -   情况2：类覆盖了 equals() 方法。一般，我们都覆盖 equals() 方法来两个对象的内容相等；若它们的内容相等，则返回 true (即，认为这两个对象相等)。

 **为什么要有 hashCode**

`我们以“HashSet 如何检查重复”为例子来说明为什么要有 hashCode：`

-   当你把对象加入 HashSet 时，HashSet 会先计算对象的 hashcode 值来判断对象加入的位置，同时也会与其他已经加入的对象的 hashcode 值作比较，如果没有相符的hashcode，HashSet会假设对象没有重复出现。但是如果发现有相同 hashcode 值的对象，这时会调用 equals()方法来检查 hashcode 相等的对象是否真的相同。如果两者相同，HashSet 就不会让其加入操作成功。如果不同的话，就会重新散列到其他位置。（摘自我的Java启蒙书《Head first java》第二版）。这样我们就大大减少了 equals 的次数，相应就大大提高了执行速度。

**hashCode()与equals()的相关规定**

-   如果两个对象相等，则hashcode一定也是相同的
    
-   两个对象相等，对两个对象分别调用equals方法都返回true
    
-   两个对象有相同的hashcode值，它们也不一定是相等的
    

`因此，equals 方法被覆盖过，则 hashCode 方法也必须被覆盖`

`hashCode() 的默认行为是对堆上的对象产生独特值。如果没有重写 hashCode()，则该 class 的两个对象无论如何都不会相等（即使这两个对象指向相同的数据）`

### 值传递

#### 值传递和引用传递有什么区别

-   值传递：指的是在方法调用时，传递的参数是按**值的拷贝传递**，传递的是值的拷贝，也就是说传递后就互不相关了。
-   引用传递：指的是在方法调用时，传递的参数是按引用进行传递，其实**传递的引用的地址**，也就是变量所对应的内存空间的地址。传递的是值的引用，也就是说传递前和传递后都指向同一个引用（也就是同一个内存空间）。

### Comparator与Comparable有什么区别？

- Comparable & Comparator 都是用来实现集合中元素的比较、排序的，只是 Comparable 是在集合内部定义的方法实现的排序，Comparator 是在集合外部实现的排序，所以，如想实现排序，就需要在集合外定义 Comparator 接口的方法或在集合内实现 Comparable 接口的方法。

- Comparator位于包java.util下，而Comparable位于包 java.lang下。

- Comparable 是一个对象本身就已经支持自比较所需要实现的接口（如 String、Integer 自己就可以完成比较大小操作，已经实现了Comparable接口） 自定义的类要在加入list容器中后能够排序，可以实现Comparable接口，在用Collections类的sort方法排序时，如果不指定Comparator，那么就以自然顺序排序， 这里的自然顺序就是实现Comparable接口设定的排序方式。

- 而 Comparator 是一个专用的比较器，当这个对象不支持自比较或者自比较函数不能满足你的要求时，你可以写一个比较器来完成两个对象之间大小的比较。

- 可以说一个是自已完成比较，一个是外部程序实现比较的差别而已。 用 Comparator 是策略模式（strategy design pattern），就是不改变对象自身，而用一个策略对象（strategy object）来改变它的行为。 比如：你想对整数采用绝对值大小来排序，Integer 是不符合要求的，你不需要去修改 Integer 类（实际上你也不能这么做）去改变它的排序行为，只要使用一个实现了 Comparator 接口的对象来实现控制它的排序就行了。

## 泛型

### 类型擦除底层

Java泛型在编译期完成，它是依赖编译器实现的。其实，编译器主要做了这些工作：

- set()方法的类型检验
- get()处的类型转换，编译器插入了一个checkcast语句

### 使用泛型的限制（没写完）

#### 不能用基本类型实例化类型化参数

不能用类型参数代替基本类型。因此， 没有 `Pair`, 只 有`Pair`。 当然, 其原因是类型擦除。擦除之后， Pair 类含有 Object 类型的域， 而 Object 不能存储 double值。

## IO

### IO结构图（需要补充）

### java 中 IO 流分为几种

按功能来分：输入流（input）、输出流（output）。

按类型来分：字节流和字符流。

字节流和字符流的区别是：字节流按 8 位传输以字节为单位输入输出数据，字符流按 16 位传输以字符为单位输入输出数据。

### BIO，AIO，NIO的区别（需要补上代码）

-   BIO：Block IO 同步阻塞式 IO，就是我们平常使用的传统 IO，它的特点是模式简单使用方便，并发处理能力低。
-   NIO：Non IO 同步非阻塞 IO，是传统 IO 的升级，客户端和服务器端通过 Channel（通道）通讯，实现了多路复用。
-   AIO：Asynchronous IO 是 NIO 的升级，也叫 NIO2，实现了异步非堵塞 IO ，异步 IO 的操作基于事件和回调机制。

-   **BIO (Blocking I/O):**  同步阻塞I/O模式，**数据的读取写入必须阻塞在一个线程内**等待其完成。在活动连接数不是特别高（小于单机1000）的情况下，这种模型是比较不错的，可以让每一个连接专注于自己的 I/O 并且编程模型简单，也不用过多考虑系统的过载、限流等问题。线程池本身就是一个天然的漏斗，可以缓冲一些系统处理不了的连接或请求。但是，当面对十万甚至百万级连接的时候，传统的 BIO 模型是无能为力的。因此，我们需要一种更高效的 I/O 处理模型来应对更高的并发量。
-   **NIO (New I/O):**  NIO是一种同步非阻塞的I/O模型，在Java 1.4 中引入了NIO框架，对应 java.nio 包，提供了 Channel , Selector，Buffer等抽象。NIO中的N可以理解为Non-blocking，不单纯是New。它支持面向缓冲的，基于通道的I/O操作方法。 NIO提供了与传统BIO模型中的  `Socket`  和  `ServerSocket`  相对应的  `SocketChannel`  和  `ServerSocketChannel`  两种不同的套接字通道实现,两种通道都支持阻塞和非阻塞两种模式。阻塞模式使用就像传统中的支持一样，比较简单，但是性能和可靠性都不好；非阻塞模式正好与之相反。对于低负载、低并发的应用程序，可以使用同步阻塞I/O来提升开发速率和更好的维护性；对于高负载、高并发的（网络）应用，应使用 NIO 的非阻塞模式来开发
-   **AIO (Asynchronous I/O):**  AIO 也就是 NIO 2。在 Java 7 中引入了 NIO 的改进版 NIO 2,它是异步非阻塞的IO模型。异步 IO 是基于事件和回调机制实现的，也就是应用操作之后会直接返回，不会堵塞在那里，当后台处理完成，操作系统会通知相应的线程进行后续的操作。AIO 是异步IO的缩写，虽然 NIO 在网络操作中，提供了非阻塞的方法，但是 NIO 的 IO 行为还是同步的。对于 NIO 来说，我们的业务线程是在 IO 操作准备好时，得到通知，接着就由这个线程自行进行 IO 操作，IO操作本身是同步的。查阅网上相关资料，我发现就目前来说 AIO 的应用还不是很广泛，Netty 之前也尝试使用过 AIO，不过又放弃了。

简介：

### BIO

同步阻塞式IO模型，由一个独立的线程负责监听客户端的连接，它接收到客户端连接请求之后为每个客户端创建一个新的线程进行处理。

缺点：缺乏弹性伸缩能力，并发访问量较大时，容易导致进程宕机或者僵死。

### 伪异步IO

当有新的客户端接入时，将客户端的Socket封装成一个Task投递到服务器的线程池中进行处理。

缺点：底层依然使用同步阻塞模型，无法从根本上解决问题。

### NIO

#### 缓冲区

包含要写入或读出的数据，所有数据都使用缓冲区处理。

实质是一个数组，最常用的为ByteBuffer，事实上每一种Java基本类型都对应有一种缓冲区。

**基本属性**：

- 容量（capacity）：表示缓冲区最大数据容量，一旦创建不能更改
- 限制（limit）：第一个不应该读取或写入的数据的索引，即位于limit后的数据不可读写
- 位置（position）：下一个要读取或写入的数据的索引。
- 标记（mark）：标记是一个索引，通过缓冲区中的mark（）方法指定缓冲区中的一个特定的position，之后可以通过调用reset()方法恢复到这个position

**常用方法**：

- `Buffer flip()`:将缓冲区的界限设置为当前位置，并将当前位置设为0，切换到读数据模式。
- `boolean hasRemaining()`：判断缓冲区中是否还有元素
- `Buffer clear()`:清空缓冲区并返回对缓冲区的引用

#### 通道

网络数据通过Channel（通道）读取和写入，是全双工的。主要有两大类：SelectableChannel（用于网络读写）和FileChannel（用于文件操作）

Java NIO是非阻塞的。当线程从某个通道进行读写数据的时候，如果没有数据可用的时候，该线程可用执行其他任务。线程通常将非阻塞IO的空间时间用于在其他通道上执行IO操作，所以单独的线程可用管理多个输入和输出通道。

**主要实体类**:

-   Java为Channel(java.nio.channels.Channel)接口提供的最主要的实现类如下：
    -   FileChannel：用于读取、写入、映射和操作文件的通道。
    -   DatagramChannel：通过UDP读写网络中的数据通道。
    -   SocketChannel：通过TCP读写网络中的数据。
    -   ServerSocketChannel：可以监听新进来的TCP连接，对每一个新进来的连接都会创建一个SocketChannel。

#### 多路复用器

多路复用器Selector会不断轮询注册在其上的Channel，如果某个Channel上面发生读或写事件，这个Channel就处于就绪状态，会被Selector轮询。

一个Selector可以同时轮询多个Channel.

可以监听的事件类型（可以使用SelectionKey的四个常量来表示）：

-   读：SelectionKey.OP_READ。
-   写：SelectionKey.OP_WRITE。
-   连接：SelectionKey.OP_CONNECT。
-   接收：SelectionKey.OP_ACCEPT。

#### 栗子

```
package com.weiwei.xu;

import org.junit.Test;

import java.io.IOException;
import java.net.InetSocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.SelectionKey;
import java.nio.channels.Selector;
import java.nio.channels.ServerSocketChannel;
import java.nio.channels.SocketChannel;
import java.util.Date;
import java.util.Iterator;

public class NOBlockingNIOTest {
    @Test
    public void client() throws IOException {
        //获取通道
        SocketChannel socketChannel = SocketChannel.open(new InetSocketAddress(9897));
        //切换成非阻塞模式
        socketChannel.configureBlocking(false);
        //分配指定大小的缓冲区
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        //发送数据给服务器端
        buffer.put(new Date().toString().getBytes());
        buffer.flip();
        socketChannel.write(buffer);
        //关闭通道
        socketChannel.close();
    }

    @Test
    public void server() throws IOException {
        //获取通道
        ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();
        //切换成非阻塞模式
        serverSocketChannel.configureBlocking(false);
        //绑定端口
        serverSocketChannel.bind(new InetSocketAddress(9897));
        //获取选择器
        Selector selector = Selector.open();
        //将通道注册到选择器上,并且指定监听事件
        serverSocketChannel.register(selector, SelectionKey.OP_ACCEPT);
        //轮询式的获取选择器上已经“准备就绪”的事件
        while (selector.select() > 0) {
            //获取当前选择器中所有注册的“选择键（已注册的监听事件）”
            Iterator<SelectionKey> iterator = selector.selectedKeys().iterator();
            //遍历
            while (iterator.hasNext()) {
                SelectionKey selectionKey = iterator.next();
                //判断具体是什么事件准备就绪
                if (selectionKey.isAcceptable()) {
                    //如果是“接受就绪”，获取客户端的连接
                    SocketChannel socketChannel = serverSocketChannel.accept();
                    //切换成非阻塞模式
                    socketChannel.configureBlocking(false);
                    //将该通道注册到选择器上
                    socketChannel.register(selector, SelectionKey.OP_READ);
                } else if (selectionKey.isReadable()) {
                    //获取当前选择器上“读就绪”状态的通道
                    SocketChannel socketChannel = (SocketChannel) selectionKey.channel();
                    //读取数据
                    ByteBuffer buffer = ByteBuffer.allocate(1024);
                    int len = 0;
                    while ((len = socketChannel.read(buffer)) != -1) {
                        buffer.flip();
                        System.out.println(new String(buffer.array(), 0, len));
                        buffer.clear();
                    }

                }
                //取消选择键
                iterator.remove();
            }


        }


    }

}

```


## 反射

### 什么是反射机制？

JAVA反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法和属性；这种**动态获取的信息以及动态调用对象的方法的功能**称为java语言的反射机制。
    
-   静态编译和动态编译
    
    -   静态编译：在编译时确定类型，绑定对象
        
    -   动态编译：运行时确定类型，绑定对象
        

### 反射机制优缺点

-   **优点：**  运行期类型的判断，动态加载类，提高代码灵活度。
-   **缺点：**  性能瓶颈：反射相当于一系列解释操作，通知 JVM 要做的事情，性能比直接的java代码要慢很多。

### 反射机制的应用场景有哪些？

-   反射是框架设计的灵魂。
    
-   在我们平时的项目开发过程中，基本上很少会直接使用到反射机制，但这不能说明反射机制没有用，实际上有很多设计、开发都与反射机制有关，例如模块化的开发，通过反射去调用对应的字节码；动态代理设计模式也采用了反射机制，还有我们日常使用的 Spring／Hibernate 等框架也大量使用到了反射机制。
    
-   举例：①我们在使用JDBC连接数据库时使用Class.forName()通过反射加载数据库的驱动程序；②Spring框架也用到很多反射机制，最经典的就是xml的配置模式。Spring 通过 XML 配置模式装载 Bean 的过程：1) 将程序内所有 XML 或 Properties 配置文件加载入内存中; 2)Java类里面解析xml或properties里面的内容，得到对应实体类的字节码字符串以及相关的属性信息; 3)使用反射机制，根据这个字符串获得某个类的Class实例; 4)动态配置实例的属性
    

### Java获取反射的三种方法

1.通过new对象实现反射机制 2.通过路径实现反射机制 3.通过类名实现反射机制

```java
public class Student {
    private int id;
    String name;
    protected boolean sex;
    public float score;
}


public class Get {
    //获取反射机制三种方式
    public static void main(String[] args) throws ClassNotFoundException {
        //方式一(通过建立对象)
        Student stu = new Student();
        Class classobj1 = stu.getClass();
        System.out.println(classobj1.getName());
        //方式二（所在通过路径-相对路径）
        Class classobj2 = Class.forName("fanshe.Student");
        System.out.println(classobj2.getName());
        //方式三（通过类名）
        Class classobj3 = Student.class;
        System.out.println(classobj3.getName());
    }
}
```

### 反射的具体应用

#### JDBC 的数据库的连接

在JDBC连接数据库中，一般包括**加载驱动，获得数据库连接**等步骤。而加载驱动，就是引入相关Jar包后，通过**Class.forName()** 即反射技术，加载数据库的驱动程序。

#### Spring 框架的使用

Spring 通过 XML 配置模式装载 Bean，也是反射的一个典型例子。

**装载过程：**

- 将程序内XML 配置文件加载入内存中
- Java类解析xml里面的内容，得到相关字节码信息
- 使用反射机制，得到Class实例
- 动态配置实例的属性，使用

## 动态代理

### JDK动态代理与cglib实现的区别

- java动态代理是利用反射机制生成一个实现代理接口的匿名类，在调用具体方法前调用InvokeHandler来处理。

- cglib动态代理是利用asm开源包，对代理对象类的class文件加载进来，通过修改其字节码生成子类来处理。

- JDK动态代理只能对实现了接口的类生成代理，而不能针对类

- cglib是针对类实现代理，主要是对指定的类生成一个子类，覆盖其中的方法。因为是继承，所以该类或方法最好不要声明成final

## 异常

### 层次结构

![](https://user-gold-cdn.xitu.io/2019/11/9/16e50d8a376c1b56?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

#### Error

表示编译时或者系统错误,error是无法处理的。

#### Exception

代码异常，Java程序员关心的基类型通常是Exception。它能被程序本身可以处理.

它可以分为RuntimeException（运行时异常）和CheckedException（可检查的异常）。

**常见的RuntimeException异常：**

```
- NullPointerException 空指针异常
- ArithmeticException 出现异常的运算条件时，抛出此异常
- IndexOutOfBoundsException 数组索引越界异常
- ClassNotFoundException 找不到类异常
- IllegalArgumentException(非法参数异常)
```

**常见的 Checked Exception 异常：**

```
- IOException (操作输入流和输出流时可能出现的异常)
- ClassCastException(类型转换异常类)
```

- Checked Exception就是编译器要求你必须处置的异常。

### 异常处理

![](https://user-gold-cdn.xitu.io/2019/11/10/16e55f2c321d909d?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

### try-catch-finally-return执行顺序

- 如果不发生异常，不会执行catch部分。

- 不管有没有发生异常，finally都会执行到。

- 即使try和catch中有return时，finally仍然会执行

- finally是在return后面的表达式运算完后再执行的。（此时并没有返回运算后的值，而是先把要返回的值保存起来，若finally中无return，则不管finally中的代码怎么样，返回的值都不会改变，仍然是之前保存的值），该情况下函数返回值是在finally执行前确定的)

- finally部分就不要return了，要不然，就回不去try或者catch的return了。

### Java7 新的 try-with-resources语句

用于自动资源管理.

- 资源是指在程序用完了之后必须要关闭的对象。

- try-with-resources保证了每个声明了的资源在语句结束的时候会被关闭

- 什么样的对象才能当做资源使用呢？只要实现了java.lang.AutoCloseable接口或者java.io.Closeable接口的对象，都OK。

```java
try(// open resources here){
    // use resources
} catch (FileNotFoundException e) {
    // exception handling
}
// resources are closed as soon as try-catch block is executed.
```

### 异常匹配

抛出异常的时候,异常处理系统会按照代码的书写顺序找出"最近"的处理程序。 找到匹配的处理程序之后,它就认为异常将得到处理,然后就不再继续查找。

查找的时候并不要求抛出的异常同处理程序的异常完全匹配。派生类的对象也可以配备其基类的处理程序

## String

### String有哪些特性

-   不变性：String 是只读字符串，是一个典型的 immutable 对象，对它进行任何操作，其实都是创建一个新的对象，再把引用指向该对象。不变模式的主要作用在于当一个对象需要被多线程共享并频繁访问时，可以保证数据的一致性。
    
-   常量池优化：String 对象创建之后，会在字符串常量池中进行缓存，如果下次创建同样的对象时，会直接返回缓存的引用。
    
-   final：使用 final 来定义 String 类，表示 String 类不能被继承，提高了系统的安全性。

### String 类的常用方法都有那些？

-   indexOf()：返回指定字符的索引。
-   charAt()：返回指定索引处的字符。
-   replace()：字符串替换。
-   trim()：去除字符串两端空白。
-   split()：分割字符串，返回一个分割后的字符串数组。
-   getBytes()：返回字符串的 byte 类型数组。
-   length()：返回字符串长度。
-   toLowerCase()：将字符串转成小写字母。
-   toUpperCase()：将字符串转成大写字符。
-   substring()：截取字符串。
-   equals()：字符串比较。

### String str="i"与 String str=new String(“i”)一样吗？

-   不一样，因为内存的分配方式不一样。String str="i"的方式，java 虚拟机会将其分配到常量池中；而 String str=new String(“i”) 则会被分到堆内存中。

### String s = new String(“xyz”);创建了几个字符串对象

-   两个对象，一个是静态区的"xyz"，一个是用new创建在堆上的对象。

### String和StringBuffer、StringBuilder的区别是什么？String为什么是不可变的

**可变性**

-   String类中使用字符数组保存字符串，private final char value[]，所以string对象是不可变的。StringBuilder与StringBuffer都继承自AbstractStringBuilder类，在AbstractStringBuilder中也是使用字符数组保存字符串，char[] value，这两种对象都是可变的。

**线程安全性**

-   String中的对象是不可变的，也就可以理解为常量，线程安全。AbstractStringBuilder是StringBuilder与StringBuffer的公共父类，定义了一些字符串的基本操作，如expandCapacity、append、insert、indexOf等公共方法。StringBuffer对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全的。StringBuilder并没有对方法进行加同步锁，所以是非线程安全的。

**性能**

-   每次对String 类型进行改变的时候，都会生成一个新的String对象，然后将指针指向新的String 对象。StringBuffer每次都会对StringBuffer对象本身进行操作，而不是生成新的对象并改变对象引用。相同情况下使用StirngBuilder 相比使用StringBuffer 仅能获得10%~15% 左右的性能提升，但却要冒多线程不安全的风险。

**对于三者使用的总结**

-   如果要操作少量的数据用 = String
    
-   单线程操作字符串缓冲区 下操作大量数据 = StringBuilder
    
-   多线程操作字符串缓冲区 下操作大量数据 = StringBuffer

## 自动装箱和拆箱

### Integer a= 127 与 Integer b = 127相等吗

-   对于对象引用类型：==比较的是对象的内存地址。
-   对于基本数据类型：==比较的是值。

`如果整型字面量的值在-128到127之间，那么自动装箱时不会new新的Integer对象，而是直接引用常量池中的Integer对象，超过范围 a1==b1的结果是false`

### int和Integer 有什么区别

- int 是基本数据类型，interger 是 int 的封装类

- int 默认值为 0 ，而interger 默认值为 null， Interger使用需要判空处理

- Integer的缓存机制：为了节省内存和提高性能，Integer类在内部通过使用相同的对象引用实现缓存和重用，Integer类默认在**-128 ~ 127**之间，可以通过 -XX:AutoBoxCacheMax进行修改，且这种机制仅在自动装箱的时候有用，在使用构造器创建Integer对象时无用。

### String的存储

早期JDK是以char[]存储的。
```
public final class String {
    private final char[] value;
    private final int offset;
    private final int count;
}
```
后来的JDK是以byte[]存储的.这样做的目的是为了节省内存，因为大量的长度较短的String通常仅包含ASCII字符
```
public final class String {
    private final byte[] value;
    private final byte coder; // 0 = LATIN1, 1 = UTF16
}
```

## Object类

### 常用方法

- `boolean equals(Object obj)` : 判断指定对象与该对象是否相等 。 此处相等的标准是 ， 两个对象是同一个对象
- `protected void finalize()` : 当系统中没有引用变量引用到该对象时，垃圾回收器调用 此方法来清理该对象的资源 。
- `Class<?> getClass()` : 返回该对象的运行时类。
- `int hashCode()` :  返回该对象的 hashCode 值.
- `String toString()` :  返回 该对象的字符串表示
- `public final void wait()`
- `public final native void notifyAll()`
- `public final native void notify()`
- `protected native Object clone()` : 用于帮助其他对 象来实现"自我克隆"，所谓"自我克隆"就是得到一个当前对象的副本，而且二者之间完全隔离。

Object 类提供的 Clone机制只对对象里各实例变量进行"简单复制"，如果实例变量的类型是引用类型， Object 的 Clone 机制也只是简单地复制这个引用变量，这样原有对象的引用类型的实例变量与克隆对象的引用类型的实例变量依然指向内存中的同一个实例.

## final关键字

- 用来修饰类，方法，变量
- final修饰的类不能被继承，类中所有成员方法都会被隐式指定为final方法。
- final修饰的方法不能被重写。
- final修饰的变量是常量，如果是基本数据类型的变量，则其数值一旦在初始化之后便不能更改，如果是引用类型的变量，则在对其初始化之后便不能让其指向另一个对象 


## Java8新特性

### 接口内允许添加默认实现的方法

Java8允许通过`default`关键字对接口中定义的抽象方法提供一个默认的实现。

```
// 定义一个公式接口
interface Formula {
    // 计算
    double calculate(int a);

    // 求平方根
    default double sqrt(int a) {
        return Math.sqrt(a);
    }
}
```

匿名对象实现`Formula`接口：
```
Formula formula = new Formula() {
    @Override
    public double calculate(int a) {
        return sqrt(a * 100);
    }
};

formula.calculate(100);     // 100.0
formula.sqrt(16);           // 4.0

```

### Lambda表达式

老版本的对一个含有字符串的集合进行排序：

```
List<String> names = Arrays.asList("peter", "anna", "mike", "xenia");

Collections.sort(names, new Comparator<String>() {
    @Override
    public int compare(String a, String b) {
        return b.compareTo(a);
    }
});

```
Java8中推荐：
```
Collections.sort(names, (String a, String b) -> {
    return b.compareTo(a);
});
```
函数式接口：**只包含一个抽象方法**的声明，针对该接口类型的所有Lambda表达式都会与这个抽象方法匹配。

Java8中接口的default默认方法不算抽象方法。

Java8允许通过`::`关键字来引用类的方法或构造器。

在Lambda表达式中，可以访问外部的final变量（可为隐式final类型），对成员变量和静态变量拥有读写权限。

带有默认实现的接口方法，可以在匿名内部类中访问，不可使用Lambda表达式访问。

### 内置函数式接口

`Predicate` 是一个可以指定入参类型，并返回 boolean 值的函数式接口。它内部提供了一些带有默认实现的方法，可以 被用来组合一个复杂的逻辑判断（`and`, `or`, `negate`）：

```
Predicate<String> predicate = (s) -> s.length() > 0;

predicate.test("foo");              // true
predicate.negate().test("foo");     // false

Predicate<Boolean> nonNull = Objects::nonNull;
Predicate<Boolean> isNull = Objects::isNull;

Predicate<String> isEmpty = String::isEmpty;
Predicate<String> isNotEmpty = isEmpty.negate();
```

`Function` 函数式接口的作用是，我们可以为其提供一个原料，他给生产一个最终的产品。通过它提供的默认方法，组合,链行处理(`compose`, `andThen`):

```
Function<String, Integer> toInteger = Integer::valueOf;
Function<String, String> backToString = toInteger.andThen(String::valueOf);

backToString.apply("123");     // "123"

```

`Supplier` 与 `Function` 不同，它不接受入参，直接为我们生产一个指定的结果，有点像生产者模式:

```
Supplier<Person> personSupplier = Person::new;
personSupplier.get();   // new Person
```

对于 `Consumer`，我们需要提供入参，用来被消费，如下面这段示例代码：

```
Consumer<Person> greeter = (p) -> System.out.println("Hello, " + p.firstName);
greeter.accept(new Person("Luke", "Skywalker"));
```

`Comparator` 在 Java 8 之前是使用比较普遍的。Java 8 中除了将其升级成了函数式接口，还为它拓展了一些默认方法：

```
Comparator<Person> comparator = (p1, p2) -> p1.firstName.compareTo(p2.firstName);

Person p1 = new Person("John", "Doe");
Person p2 = new Person("Alice", "Wonderland");

comparator.compare(p1, p2);             // > 0
comparator.reversed().compare(p1, p2);  // < 0
```
### Optional

设计它的目的是为了防止空指针异常(NullPointerException).

Optional 类是一个可以为null的容器对象。如果值存在则isPresent()方法会返回true，调用get()方法会返回该对象。

```
Optional<String> optional = Optional.of("bam");

optional.isPresent();           // true
optional.get();                 // "bam"
optional.orElse("fallback");    // "bam"

optional.ifPresent((s) -> System.out.println(s.charAt(0)));     // "b"

```

### Stream流

可以使用`java.util.Stream`对一个包含一个或多个元素的集合做各种操作（中间操作或终端操作）。

只能对实现了`java.util.Collection`接口的类做流的操作。

eg：

```
package com.alone.test.java8;  
  
import org.junit.Test;  
  
import java.util.ArrayList;  
import java.util.List;  
import java.util.Optional;  
import java.util.UUID;  
import java.util.concurrent.TimeUnit;  
import java.util.stream.Collectors;  
  
/**  
 * @BelongsProject: JavaSourceNotes  
 * @BelongsPackage: com.alone.test.java8  
 * @Author: Alone  
 * @CreateTime: 2020-10-04 20:26  
 * @Description: Stream流的使用  
  */  
public class StreamTest {  
  
    /**  
 * filter 过滤  
  */  
  @Test  
  public void test1(){  
        List<String> list = new ArrayList<>();  
        list.add("ddd2");  
        list.add("aaa2");  
        list.add("bbb1");  
        list.add("aaa3");  
        list.add("ccc");  
        list.add("bbb2");  
        list.add("ddd1");  
  
        //filter的入参是一个Predicate,返参同样是一个Stream流,forEach是一个终端操作，打印被筛选的元素  
  list.stream()  
                .filter((s) -> s.startsWith("a"))  
                .forEach(System.out::println);  
    }  
  
    @Test  
  public void test2() {  
        List<String> list = new ArrayList<>();  
        list.add("ddd2");  
        list.add("aaa2");  
        list.add("bbb1");  
        list.add("aaa3");  
        list.add("ccc");  
        list.add("bbb2");  
        list.add("ddd1");  
  
        list.stream()  
                .sorted()  
                .filter((s) -> s.startsWith("a"))  
                .forEach(System.out::println);  
  
        //sorted不会对list做出任何改变,list还是原有的那些元素,且顺序不变  
  System.out.println(list);  
  
        List<String> sortedList = list.stream()  
                .sorted()  
                .filter((s) -> s.startsWith("a"))  
                .collect(Collectors.toList());//将流转换为list  
  System.out.println(sortedList);  
    }  
  
    @Test  
  public void test3() {  
        List<String> list = new ArrayList<>();  
        list.add("ddd2");  
        list.add("aaa2");  
        list.add("bbb1");  
        list.add("aaa3");  
        list.add("ccc");  
        list.add("bbb2");  
        list.add("ddd1");  
  
        //将每一个元素做功能处理  
  list.stream()  
                .map(String::toUpperCase)  
                .sorted((a, b) -> b.compareTo(a))  
                .forEach(System.out::println);  
    }  
  
    /**  
 * match用来做匹配操作  
  * 返回值是一个boolean类型  
  * 可以方便验证一个list中是否存在某个类型的元素  
  */  
  @Test  
  public void test4() {  
        List<String> list = new ArrayList<>();  
        list.add("ddd2");  
        list.add("aaa2");  
        list.add("bbb1");  
        list.add("aaa3");  
        list.add("ccc");  
        list.add("bbb2");  
        list.add("ddd1");  
  
        //验证list中string是否有以a开头的,匹配到第一个,即返回true  
  boolean anyStartsWithA = list.stream()  
                .anyMatch((s) -> s.startsWith("a"));  
        System.out.println(anyStartsWithA);  
  
        //验证list中string是否都是以a开头的  
  boolean allStartsWithA = list.stream()  
                .allMatch((s) -> s.startsWith("a"));  
        System.out.println(allStartsWithA);  
  
        //验证list中string是否都不是以z开头的  
  boolean noneStartsWithZ = list.stream()  
                .noneMatch((s) -> s.startsWith("z"));  
        System.out.println(noneStartsWithZ);  
    }  
  
    /**  
 * count是一个终端操作  
  * 用于统计stream流中的元素总数  
  */  
  @Test  
  public void test5() {  
        List<String> list = new ArrayList<>();  
        list.add("ddd2");  
        list.add("aaa2");  
        list.add("bbb1");  
        list.add("aaa3");  
        list.add("ccc");  
        list.add("bbb2");  
        list.add("ddd1");  
  
        long startsWithB = list.stream()  
                .filter((s) -> s.startsWith("b"))  
                .count();  
        System.out.println(startsWithB);  
    }  
  
    /**  
 * 通过入参的function将list归约成一个值,返回类型为Optional类型  
  */  
  @Test  
  public void test6() {  
        List<String> list = new ArrayList<>();  
        list.add("ddd2");  
        list.add("aaa2");  
        list.add("bbb1");  
        list.add("aaa3");  
        list.add("ccc");  
        list.add("bbb2");  
        list.add("ddd1");  
  
        Optional<String> reduced = list.stream()  
                .sorted()  
                .reduce((s1, s2) -> s1 + "#" + s2);  
        reduced.ifPresent(System.out::println);  
    }  
  
    /**  
 * 顺序流排序和并行流排序  
  * 并行流比顺序流快一倍  
  */  
  @Test  
  public void test7() {  
        int max = 1000000;  
        List<String> values = new ArrayList<>(max);  
        for (int i = 0; i < max; i++) {  
            UUID uuid = UUID.randomUUID();  
            values.add(uuid.toString());  
        }  
  
        long t0 = System.nanoTime();//纳秒  
  long count = values.stream().sorted().count();  
        System.out.println(count);  
  
        long t1 = System.nanoTime();  
        //纳秒转微秒  
  long millis = TimeUnit.NANOSECONDS.toMillis(t1 - t0);  
        System.out.println(String.format("顺序流排序耗时: %d ms", millis));  
  
        // 纳秒  
  long t2 = System.nanoTime();  
  
        long count1 = values.parallelStream().sorted().count();  
        System.out.println(count);  
  
        long t3 = System.nanoTime();  
  
        // 纳秒转微秒  
  long millis1 = TimeUnit.NANOSECONDS.toMillis(t3 - t2);  
        System.out.println(String.format("并行流排序耗时: %d ms", millis1));  
  
    }  
}
```

## 设计模式

**单例模式**特点：

-   单例类只能有一个实例。
-   单例类必须自己创建自己的唯一实例。
-   单例类必须给所有其他对象提供这一实例。

**桥接模式**特点：

-   将抽象部分与它实现部分分离，使他们都可以独立变化，抽象类和子类实现自己的对象

**组合模式**特点：

-   将对象组合成树形结构以表示‘部分-整体’的层次结构。组合模式使得用户对单个对象和组合对象的使用具有一致性

**外观模式**特点：

-   为子系统中一组接口提供一个一致的界面，此模式定义了一个高层接口