# ReviewNotes

- [面试题汇总](#-----)
  * [基础](#--)
    + [**面向对象的特性有哪些？**](#---------------)
    + [**Java中覆盖和重载是什么意思？**](#--java--------------)
      - [**构成重载的条件**](#-----------)
      - [**函数的返回值不同不可以构成重载**](#-------------------)
    + [**抽象类和接口的区别有哪些？**](#-----------------)
      - [**抽象类和接口如何选择？**](#---------------)
    + [**Java和C++的区别**](#--java-c-------)
    + [**Java中的值传递和引用传递**](#--java------------)
    + [**JDK中常用的包有哪些？**](#--jdk-----------)
    + [JDK，JRE和JVM的联系和区别](#jdk-jre-jvm------)
    + [注解](#--)
      - [Java中的注解](#java----)
      - [定义注解类](#-----)
      - [使用注解的目标](#-------)
      - [注解的属性](#-----)
      - [注解的作用目标](#-------)
      - [注解的保留策略（@Rentention）](#---------rentention-)
      - [注解处理器](#-----)
    + [泛型](#--)
      - [Java的泛型是如何工作的 ? 什么是类型擦除 ?](#java---------------------)
      - [什么是泛型中的限定通配符和非限定通配符 ?](#---------------------)
      - [List<? extends T>和List <? super T>之间有什么区别 ?](#list---extends-t--list----super-t----------)
    + [反射](#--)
      - [获取Class对象的3种方法](#--class---3---)
      - [创建对象的两种方法](#---------)
      - [Field类的使用](#field----)
      - [Constructor类的使用](#constructor----)
      - [Method类的使用](#method----)
      - [AccessibleObject的使用](#accessibleobject---)
  * [集合](#--)
    + [**说说常见的集合有哪些吧？**](#----------------)
    + [List和Set的区别](#list-set---)
    + [List、Set和Map的初始容量和加载因子](#list-set-map----------)
    + [HashMap和Hashtable的区别有哪些？](#hashmap-hashtable-------)
    + [**HashMap的底层实现你知道吗？**](#--hashmap------------)
    + [**HashMap的长度为什么是2的幂次方**](#--hashmap-------2------)
    + [**ConcurrentHashMap和Hashtable的区别？**](#--concurrenthashmap-hashtable------)
    + [**ConcurrentHashMap的具体实现**](#--concurrenthashmap-------)
    + [**Comparable接口和Comparator接口有什么区别**](#--comparable---comparator---------)
    + [快速失败机制(fail-fast)](#-------fail-fast-)
    + [HashSet](#hashset)
    + [TreeSet](#treeset)
      - [特点](#--)
      - [排序方式](#----)
  * [多线程](#---)
    + [**如何指定多个线程的执行顺序**](#-----------------)
    + [**线程和进程的区别**](#------------)

# 面试题汇总

## 基础

### **面向对象的特性有哪些？**

- 封装

  把一个对象的状态信息（也就是属性）隐藏在对象内部，不允许外部对象直接访问对象的内部信息。但是可以提供一些可以被外界访问的方法来操作属性。

- 继承

  使用已存在的类的定义作为基础建立新类的技术，新类的定义可以增加新的数据或新的功能，也可以用父类的功能。

  1.子类**拥有**父类对象所有的属性和方法（包括私有属性和私有方法），但是父类中的私有属性和方法子类无法访问。

  2.子类可以拥有自己的属性和方法，即子类可以对父类进行扩展。

  3.子类可以用自己的方式实现父类的方法。

- 多态

  一个对象具有多种的状态，具体表现为父类的引用指向子类的实例。

  特点：

  1.对象类型不可变，引用类型可变

  2.方法具有多态性，属性不具有多态性

  3.引用类型变量发出的方法调用的到底是哪个类中的方法，必须在程序运行期间才能确定

  4.多态不能调用“只在子类存在但不在父类存在的方法”

  5.如果子类重写了父类的方法，真正执行的是子类覆盖的方法，如果子类没有覆盖父类的方法，执行的是父类的方法

### **Java中覆盖和重载是什么意思？**

覆盖（Override）是指子类对父类方法的一种重写，只能比父类<font color="red">抛出更少的异常</font>，<font color="red">访问权限</font>不能比父类的小。被覆盖的方法<font color="red">不能是private</font>的，否则只是在子类中重新定义了一个方法；

重载（Overload）表示同一个类中可以有多个名称相同的方法，但这些方法的<font color="red">参数列表</font>各不相同。

总结：

| 区别点     | 重载方法 | 重写方法                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| 发生范围   | 同一个类 | 子类                                                         |
| 参数列表   | 必须修改 | 一定不能修改                                                 |
| 返回类型   | 可修改   | 子类方法返回值类型应比父类方法返回值类型更小或相等           |
| 异常       | 可修改   | 子类方法声明抛出的异常类应比父类方法声明抛出的异常类更小或相等； |
| 访问修饰符 | 可修改   | 一定不能做更严格的限制（可以降低限制）                       |
| 发生阶段   | 编译期   | 运行期                                                       |

#### **构成重载的条件**

参数类型不同、参数个数不同、参数顺序不同。

#### **函数的返回值不同不可以构成重载**

因为Java中调用函数并不需要强制赋值。eg:

```java
void f(){}
int f(){ return 1;}
```

只要编译器可以根据语境明确判断出语义，比如在int x = f();中，那么的确可以据此区分重载方法。不过，**有时你并不关心方法的返回值，你想要的是方法调用的其他效果**（这常被称为“为了副作用而调用”），这时你可能会调用方法而忽略其返回值，所以如果像下面的调用：

```java
fun();
```

此时Java如何才能判断调用的是哪一个 f() 呢？别人如何理解这种代码呢？**所以，根据方法返回值来区分重载方法是行不通的。**

### **抽象类和接口的区别有哪些？**

- 抽象类中可以没有抽象方法；接口中的方法必须是抽象方法；

- 抽象类中可以有普通的成员变量；接口中的变量必须是static final类型的，必须被初始化,接口中只有常量，没有变量。

- 抽象类只能单继承，接口可以继承多个父接口；

- Java8中接口中会有default方法，即方法可以被实现。

#### **抽象类和接口如何选择？**

1. 如果要创建<font color="red">不带任何方法定义和成员变量</font>的基类，那么就应该选择接口而不是抽象类。

2. 如果知道某个类应该是基类，那么第一个选择的应该是让它成为一个接口，只有在<font color="red">必须要有方法定义和成员变量</font>的时候，才应该选择抽象类。因为抽象类中允许存在一个或多个<font color="red">被具体实现</font>的方法，只要方法没有被全部实现该类就仍是抽象类。

### **Java和C++的区别**

- 都是面向对象的语言，都支持封装、继承和多态

- 指针：Java不提供指针来直接访问内存，程序更加安全

- 继承： Java的类是单继承的，C++支持多重继承； Java通过一个类实现多个接口来实现C++中的多重继承； Java中类不可以多继承，但是！！！接口可以多继承

- 内存： Java有自动内存管理机制，不需要程序员手动释放无用内存

### **Java中的值传递和引用传递**

值传递是指对象被值传递，意味着传递了对象的一个副本，即使副本被改变，也不会影响源对象。

引用传递是指对象被引用传递，意味着传递的并不是实际的对象，而是对象的引用。因此，外部对引用对象的改变会反映到所有的对象上。

**example 1:**

```java
public static void main(String[] args) {
    int num1 = 10;
    int num2 = 20;

    swap(num1, num2);

    System.out.println("num1 = " + num1);
    System.out.println("num2 = " + num2);
}

public static void swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;

    System.out.println("a = " + a);
    System.out.println("b = " + b);
}
```

结果：

```
a = 20
b = 10
num1 = 10
num2 = 20
```

解析：

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/example1.png)

**example2:**

```java
public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 5 };
		System.out.println(arr[0]); // 1
		change(arr);
		System.out.println(arr[0]); // 0
	}

	public static void change(int[] array) {
		// 将数组的第一个元素变为0
		array[0] = 0;
	}
}
```

解析：

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/example2.jpg)

**example 3:**

```java
public class Test {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Student s1 = new Student("小张");
		Student s2 = new Student("小李");
		Test.swap(s1, s2);
		System.out.println("s1:" + s1.getName());
		System.out.println("s2:" + s2.getName());
	}

	public static void swap(Student x, Student y) {
		Student temp = x;
		x = y;
		y = temp;
		System.out.println("x:" + x.getName());
		System.out.println("y:" + y.getName());
	}
}
```

解析：

交换前：

![](https://camo.githubusercontent.com/9d6dd0313695d309280675cd3251b47432a28814/687474703a2f2f6d792d626c6f672d746f2d7573652e6f73732d636e2d6265696a696e672e616c6979756e63732e636f6d2f31382d392d32372f38383732393831382e6a7067)

交换后：

![](https://camo.githubusercontent.com/6bea9b0ed65609d699207ab787f631f7ba0a9246/687474703a2f2f6d792d626c6f672d746f2d7573652e6f73732d636e2d6265696a696e672e616c6979756e63732e636f6d2f31382d392d32372f33343338343431342e6a7067)

**方法并没有改变存储在变量 s1 和 s2 中的对象引用。swap 方法的参数 x 和 y 被初始化为两个对象引用的拷贝，这个方法交换的是这两个拷贝**

下面再总结一下 Java 中方法参数的使用情况：

- 一个方法不能修改一个基本数据类型的参数（即数值型或布尔型）。
- 一个方法可以改变一个对象参数的状态。
- 一个方法不能让对象参数引用一个新的对象。

### **JDK中常用的包有哪些？**

java.lang、java.util、java.io、java.net、java.sql

### JDK，JRE和JVM的联系和区别

JDK是 java<font color="red">开发工具包</font>，是<font color="red">java开发环境的核心组件</font>，并提供编译、调试和运行一个java程序所需要的所有工具，可执行文件和二进制文件，是一个平台特定的软件。

JRE是 java<font color="red">运行时环境</font>，是<font color="red">JVM的实施实现</font>，提供了<font color="red">运行java程序的平台</font>。JRE包含了JVM，但是不包含java编译器/调试器之类的开发工具。

JVM是 java<font color="red">虚拟机</font>，当我们运行一个程序时，JVM负责将字节码转换为特定机器代码，JVM提供了内存管理/垃圾回收和安全机制等。这种独立于硬件和操作系统，正是java程序可以一次编写多处执行的原因。

**区别：**

1. JDK用于开发，JRE用于运行java程序

2. JDK和JRE中都包含JVM

3. JVM是java编程语言的核心并且具有平台独立性

### 注解

**语法** : @注解名称

**作用** : 替代xml配置文件

#### Java中的注解

- @Overrid：作用在方法上的注解。当方法不是重写父类的方法时会报错；

- @Deprecated：作用在方法上。标记该方法为作废方法（已过时）；

- @SuppressWarnings：作用在方法上，**压制警告**。

#### 定义注解类

定义注解类不能使用class、enum，也不能使用interface，而是使用**@interface**。

eg：

```java
public @interface MyAnn{}  
```

#### 使用注解的目标

注解可以使用在**类（接口或枚举）、属性、方法、构造器、包、参数、局部变量**。

#### 注解的属性

定义注解时，也可以给出属性。

```java
public @interface MyAnn {  
    String value();  
    int value1();  
}
```

其中value就是属性.

**使用注解**:

```java
@MyAnn(value1=100,value="hello")  
public class MyClass {  
} 
```

注解的属性还可以有默认值，在使用注解时就可以不给带有默认值的属性赋值了。但没有给出默认值的属性还是要赋值的。

```java
public @interface MyAnn {  
    String value() default "hello world";   
    int value1();  
}  
@MyAnn(value1=100)   
public class MyClass {  
} 
```

在使用注解时，如果只给名为value的属性赋值，那么可以不给出属性的名称直接给出值.

```java
public @interface MyAnn {  
    String value() default "hello world";  
    int value1() default 100;  
}  
@MyAnn()   
public class MyClass {  
}  
@MyAnn(value="hello")   
public class MyClass {  
}  
@MyAnn(value1=200)   
public class MyClass {  
}  
@MyAnn(value="hello",value1=200)   
public class MyClass {  
}  
@MyAnn("hello annocation")   
public class MyClass {  
}  
@MyAnn(300)   
public class MyClass {  
}  
@MyAnn("hello",value1=200)   
public class MyClass {  
}  
```

- 注解的属性后面要有一对圆括号，而且圆括号内不能给出东西。就像是无参的方法一样；
- 注解的属性类型只能是：基本类型、String、Enum、Class、注解类型、以上类型的一维数组类型；
- 注解的属性可以有默认值，例如：int a() default 100;
- 数组的属性默认值：`int[] arr() default {1,2,3}`，这里不能使用`new int[]{1,2,3}`
- 使用注解时，在给数组属性赋值时的格式：@MyAnn(arr={1,2,3})；

#### 注解的作用目标

在定义注解时可以限制注解的作用目录！例如让注解只能作用在类和方法上。这需要使用元注解：**@Target**。该注解有一个属性value，类型为ElementType[]，它是枚举类型。

Target注解的源码如下：

```java
public @interface Target {  
    ElementType[] value();  
}  
public enum ElementType {  
  TYPE,FIELD,METHOD,PARAMETED,CONSTRUCTOR,LOCAL_VARIABLE,ANNOCATION_TYPE,PACKAGE  
}  
```

#### 注解的保留策略（@Rentention）

- 注解的保留策略是指，注解是只保留在源代码上，还是保留到class文件上，再或者是类在运行时，可以被类加载器加载到内存中。

- 如果希望注解被反射，那么注解就要保留到运行时，而不是源代码或类文件上。
- 指定注解的保留策略需要使用元注解@Retention，它有一个value属性，类型为RetentionPolicy类型，RetentionPolicy是枚举类型

```java
public @interface Retention {  
    RetentionPolicy value();  
}  
public enum RetentionPolicy {  
    SOURCE, CLASS, RUNTIME  
} 
```

#### 注解处理器

要求：定义一个注解 @Retry ，该注解的功能是每隔一定的时间执行一次该方法，一共执行指定的次数。

解析：

定义如下的注解

```java
import java.lang.annotation.Retention;
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;
import java.lang.annotation.RetentionPolicy;
 
@Target(ElementType.METHOD) // 指明该注解的作用范围是方法上
@Retention(RetentionPolicy.RUNTIME)  // 指明该注解在运行时仍保留
public @interface Retry {
	int interval() default 3; // 定义属性，并且拥有默认值
	int time() default 3000;
}
```

接着是我们的注解处理器：

```java
// 注解处理器，定义注解的逻辑处理
class RetryProcessor {
	public void parseMethod(Class<?> clazz) throws Exception{
		Method[] methods = clazz.getDeclaredMethods(); // 根据.class得到 该类中的method
		for(final Method method : methods){
			Retry retry = method.getAnnotation(Retry.class); // 得到该method上的注解信息，可以为null
			if(retry != null){
				final int interval = retry.interval();  // 获得注解的属性
				final int time = retry.time();
				// 建立一个线程，并且执行method.invoke()方法
				ExecutorService executorService = Executors.newFixedThreadPool(2);
				executorService.execute(new Runnable() {
					@Override
					public void run() {
						for (int i = 0; i < interval; i++) {
							try {
								// 通过反射执行方法
								method.invoke(new Object(), "57890");
								Thread.sleep(time);
							} catch (Exception e) {
								e.printStackTrace();
							}
						}
					}
				});
			}
		}
	}
}
```

测试类:

```java
public class RetryTest {
	/*@Retry
	public static void sayHello(){
		System.out.println("Hello World");
	}*/ //如果要使用该方法时，method.invoke(new Object(),null)即可
	@Retry
	public static void sayHello(String name){
		System.out.println("say hello1 " + name);
	}
	@Retry(interval = 2, time = 9000)
	public static void sayHello2(String name){
		System.out.println("say hello2 " + name);
	}
	public static void main(String[] args) throws Exception {
		RetryProcessor retry = new RetryProcessor();
		retry.parseMethod(RetryTest.class);
	}
}
```

### 泛型

#### Java的泛型是如何工作的 ? 什么是类型擦除 ?

泛型是通过类型擦除来实现的，编译器在编译时擦除了所有类型相关的信息，所以在运行时不存在任何类型相关的信息。

#### 什么是泛型中的限定通配符和非限定通配符 ?

有两种限定通配符，一种是`<? extends T>`它通过确保类型必须是T的子类来设定类型的上界，另一种是`<? super T>`它通过确保类型必须是T的父类来设定类型的下界。泛型类型必须用限定内的类型来进行初始化，否则会导致编译错误。另一方面`<?>`表示了非限定通配符，因为`<?>`可以用任意类型来替代。

####  List<? extends T>和List <? super T>之间有什么区别 ?

`List<? extends T>`可以接受任何继承自T的类型的List，而`List<? super T>`可以接受任何T的父类构成的List。

### 反射

反射机制的**定义**：动态获取的信息以及动态调用对象的方法的功能

**功能**：

（1）在运行时判断任意一个对象所属的类；

（2）在运行时构造任意一个类的对象；

（3）在运行时判断任意一个类所具有的成员变量和方法；

（4）在运行时调用任意一个对象的方法；生成动态代理。

**相关类**:

**Class**：表示类、**Field**：表示成员变量、 **Method**：表示方法、**Constructor**：表示构造器。

#### 获取Class对象的3种方法

- 调用某个对象的`getClass()`方法

  ```java
  Person p = new Person();
  Class clazz = p.getClass();
  ```

- 调用某个类的class属性来获取该类对应的Class对象

  ```java
  Class clazz = Person.class;
  ```

- 使用Class类中的`forName()`静态方法(最安全/性能最好)

  ```java
  Class clazz = Class.forName("类的全路径");
  ```

#### 创建对象的两种方法

- 调用Class对象的`newInstance()`方法

  使用Class对象的`newInstance()`方法来创建该Class对象对应类的实例,但是要求该Class对象对应的类<font color="red">有默认的空构造器</font>

- 调用Constructor对象的`newInstance()`

  先使用Class对象获取指定的Constructor对象,再调用Constructor对象的`newInstance()`方法来创建Class对象对应类的实例，通过这种方法可以选定构造方法创建实例。

```java
//获取Person类的Class对象
Class clazz = Class.forName("reflection.Person");
//使用.newInstance方法创建对象
Person p = (Person)clazz.newInstance();
//获取构造方法并创建对象
Constructor c = clazz.getDeclaredConstructor(String.class, String.class, int.class);
//创建对象并设置属性
Person p1 = (Person)c.newInstance("李四", "男", 20);
```

#### Field类的使用

（1）获取Field对象

获取Field对象需要使用Class对象，下面是Class类的API：

`Field getField(String name)`：通过名字获取<font color="red">公有成员变量</font>的反射对象，<font color="red">包含父类</font>中声明的公有成员变量；

`Field[] getFields()`：获取所有公有成员变量反射对象，包含父类中声明的公有成员变量；

`Field getDeclaredField(String name)`：通过名字获取<font color="red">本类</font>中某个成员变量，<font color="red">包含本类的private成员变量</font>，但父类中声明的任何成员变量都不包含；

`Field[] getDeclaredFields()`：获取本类中声明的<font color="red">所有成员变量</font>，包含private成员变量，但不包含父类中声明的任何成员变量；

(2）Field类的常用方法

`String getName()`：获取成员变量名；

`Class getDeclaringClass()`：获取声明该成员变量的全类名；

`Class getType()`：获取当前成员变量的类型；

`Object get(Object obj)`：获取obj对象的成员变量的值；

`void set(Object obj, Object value)`：设置obj对象的成员变量值为value；

eg:

```java
public class User {
	public String username;
	public String password;
 
	public User() {
	}
 
	public User(String username, String password) {
		this.username = username;
		this.password = password;
	}
 
	public String getUsername() {
		return username;
	}
 
	public void setUsername(String username) {
		this.username = username;
	}
 
	public String getPassword() {
		return password;
	}
 
	public void setPassword(String password) {
		this.password = password;
	}
 
	@Override
	public String toString() {
		return "User [username=" + username + ", password=" + password + "]";
	}
}
```

测试:

```java
/**
     * Fields类的使用
     */
    @Test
    public void test1() throws Exception {
        String className = "com.alone.test.basic.User";
        Class clazz = Class.forName(className);//获取class对象
        User user1 = (User)clazz.newInstance();//动态创建对象
//        User user = new User("zhangSan", "123");

        Field field1 = clazz.getField("username");
        Field field2 = clazz.getField("password") ;

        //获取成员变量值
        String username = (String)field1.get(user1);
        String password = (String)field2.get(user1);

        System.out.println(username + ", " + password); // null, null

        //为成员变量设置值
        field1.set(user1, "liSi");
        field2.set(user1, "456");

        System.out.println(user1);//User [username=liSi, password=456]
        System.out.println("--------------------");

        Field[] fields = clazz.getDeclaredFields();
        for (Field field : fields) {
            System.out.println(field.getName());
            System.out.println(field.getDeclaringClass());
            System.out.println(field.getType());
        }
    }
```

结果：

```
null, null
User [username=liSi, password=456]
--------------------
username
class com.alone.test.basic.User
class java.lang.String
password
class com.alone.test.basic.User
class java.lang.String
```

#### Constructor类的使用

(1）获取Constructor对象

获取Constructor对象需要使用Class对象，下面API来自Class类：

`Constructor getConstructor(Class… parameterTypes)`：通过指定的参数类型获取公有构造器反射对象；

`Constructor[] getConstructors()`：获取所有公有构造器对象；

`Constructor getDeclaredConstructor(Class… parameterTypes)`：通过指定参数类型获取构造器反射对象。可以是私有构造器对象；

`Constructor[] getDeclaredConstructors()`：获取所有构造器对象。包含私有构造器；

(2）Constructor类常用方法

 `String getName()`：获取构造器名；

`Class getDeclaringClass()`：获取构造器所属的类型；

`Class[] getParameterTypes()`：获取构造器的所有参数的类型；

 `Class[] getExceptionTypes()`：获取构造器上声明的所有异常类型；

 `newInstance(Object… initargs)`：通过构造器反射对象调用构造器。

eg:

测试方法:

```java
	@Test
    public void test2() throws NoSuchMethodException, IllegalAccessException, InvocationTargetException, InstantiationException {
        //获取class对象
        Class clazz = User.class;
        //获取公有构造器
        Constructor constructor = clazz.getDeclaredConstructor(String.class, String.class);
        //创建对象
        User alone = (User)constructor.newInstance("Alone", "12345678");
        System.out.println(alone);
        //获取构造器名
        String name = constructor.getName();
        //获取构造器所属类型
        Class declaringClass = constructor.getDeclaringClass();
        System.out.println(declaringClass);
        //获取构造器所有参数的类型
        Class[] parameterTypes = constructor.getParameterTypes();
        for (Class parameterType : parameterTypes) {
            System.out.println(parameterType.getName());
        }
        //获取构造器上声明的所有异常类型
        Class[] exceptionTypes = constructor.getExceptionTypes();
        for (Class exceptionType : exceptionTypes) {
            System.out.println(exceptionType);
        }
    }
```

结果:

```
User [username=Alone, password=12345678]
class com.alone.test.basic.User
java.lang.String
java.lang.String
```

#### Method类的使用

（1）获取Method

获取Method需要通过Class对象，下面是Class类的API：

`Method getMethod(String name, Class… parameterTypes)`：通过方法名和方法参数类型获取方法反射对象，包含父类中声明的公有方法，但不包含所有私有方法；

`Method[] getMethods()`：获取所有公有方法，包含父类中的公有方法，但不包含任何私有方法；

`Method getDeclaredMethod(String name, Class… parameterTypes)`：通过方法名和方法参数类型获取本类中声明的方法的反射对象，包含本类中的私有方法，但不包含父类中的任何方法；

`Method[] getDeclaredMethods()`：获取本类中所有方法，包含本类中的私有方法，但不包含父类中的任何方法。

（2）Method常用方法

`String getName()`：获取方法名；

`Class getDeclaringClass()`：获取方法所属的类型；

`Class[] getParameterTypes()`：获取方法的所有参数的类型；

`Class[] getExceptionTypes()`：获取方法上声明的所有异常类型；

`Class getReturnType()`：获取方法的返回值类型；

`Object invoke(Object obj, Object… args)`：通过方法反射对象调用方法，如果当前方法是实例方法，那么当前对象就是obj，如果当前方法是static方法，那么可以给obj传递null。args表示是方法的参数；

eg:

```java
@Test
    public void test3() throws IllegalAccessException, InstantiationException, NoSuchMethodException, InvocationTargetException {
        //获取class对象
        Class clazz = User.class;
        //获取公有构造器
        Constructor constructor = clazz.getDeclaredConstructor(String.class, String.class);
        //创建对象
        User alone = (User)constructor.newInstance("Alone", "12345678");

        //获取toString方法
        Method method = clazz.getMethod("toString");
        System.out.println(method.getName());
        System.out.println(method.getDeclaringClass());
        Class<?>[] parameterTypes = method.getParameterTypes();
        for (Class<?> parameterType : parameterTypes) {
            System.out.println(parameterType);
        }
        Class<?>[] exceptionTypes = method.getExceptionTypes();
        for (Class<?> exceptionType : exceptionTypes) {
            System.out.println(exceptionType);
        }
        //调用方法
        String result = (String)method.invoke(alone);
        System.out.println(result);
    }
```

结果：

```
toString
class com.alone.test.basic.User
User [username=Alone, password=12345678]
```

#### AccessibleObject的使用

AccessibleObject类是Constructor、Method、Field三个类的父类。AccessibleObject最为重要的方法如下：

`boolean isAccessible()`：判断当前成员是否可访问；

`void setAccessible(boolean flag)`：设置当前成员是否可访问。

当Constructor、Method、Field为私有时，如果我们想反射操作，那么就必须先调用反射对象的`setAccessible(true)`方法，然后才能操作。



**工厂方法模式利用Java的反射机制来得到Class类，利用newInstance(  )方法来创建一个对象。**

eg:

![](https://img-blog.csdn.net/20160808105919728?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

```java
//抽象产品类
public abstract class Product {    
    //产品类的公共方法
    public void method1(){
            //业务逻辑处理
    }  
    //抽象方法
    public abstract void method2();    
}
 
//多个具体产品类
public class ConcreteProduct1 extends Product {
    public void method2() {
            //业务逻辑处理
    }
}
public class ConcreteProduct2 extends Product {
    public void method2() {
            //业务逻辑处理
    }
}
 
//抽象工厂类
public abstract class Creator {    
    /*
     * 创建一个产品对象，其输入参数类型可以自行设置
     * 通常为String、Enum、Class等，当然也可以为空
     */        
    public abstract <T extends Product> T create Product(Class<T> c);
}
 
//具体工厂类
public class ConcreteCreator extends Creator {     
    public <T extends Product> T create Product(Class<T> c){
            Product product=null;
            try {
                   product = (Product)Class.forName(c.get Name()).new Instance();
            } catch (Exception e) {
                   //异常处理
            }
            return (T)product;         
    }
}
```

测试代码:

```java
public class Client {
    public static void main(String[] args) {
            Creator creator = new ConcreteCreator();
            Product product = creator.createProduct(ConcreteProduct1.class);
            /*
             * 继续业务处理
             */
    }
}
```

## 集合

### **说说常见的集合有哪些吧？**

Map接口和Collection接口是所有集合框架的父接口：

1. Collection接口的子接口包括：Set接口和List接口

2. Map接口的实现类主要有：HashMap、TreeMap、Hashtable、ConcurrentHashMap以及Properties等

3. Set接口的实现类主要有：HashSet、TreeSet、LinkedHashSet等

4. List接口的实现类主要有：ArrayList、LinkedList、Stack以及Vector等

### List和Set的区别

List元素是有序的，可以重复；Set元素是无序的，不可以重复。

### List、Set和Map的初始容量和加载因子

**1. List**

- **ArrayList**的初始容量是10；加载因子为0.5； 扩容增量：原容量的 0.5倍+1；一次扩容后长度为10*1.5+1=16。
- **Vector**初始容量为10，加载因子是1。扩容增量：原容量的 1倍，如 Vector的容量为10，一次扩容后是容量为20。

**2. Set**

- **HashSet**，初始容量为16，加载因子为0.75； 扩容增量：原容量的 1 倍； 如 HashSet的容量为16，一次扩容后容量为32

**3. Map**

- **HashMap**，初始容量16，加载因子为0.75； 扩容增量：原容量的 1 倍； 如 HashMap的容量为16，一次扩容后容量为32
- **HashTable**,初始容量11，之后每次扩充，容量变为原来的 2n+1。

### HashMap和Hashtable的区别有哪些？

1. HashMap没有考虑同步，是线程不安全的；Hashtable使用了synchronized关键字，是线程安全的；

2. 前者允许null作为Key；后者不允许null作为Key

### **HashMap的底层实现你知道吗？**

JDK1.8 之前 `HashMap` 底层是 **数组和链表** 结合在一起使用也就是 **链表散列**。**HashMap 通过 key 的 hashCode 经过扰动函数处理过后得到 hash 值，然后通过 (n - 1) & hash 判断当前元素存放的位置（这里的 n 指的是数组的长度），如果当前位置存在元素的话，就判断该元素与要存入的元素的 hash 值以及 key 是否相同，如果相同的话，直接覆盖，不相同就通过拉链法解决冲突。**

**所谓扰动函数指的就是 HashMap 的 hash 方法。使用 hash 方法也就是扰动函数是为了防止一些实现比较差的 hashCode() 方法 换句话说使用扰动函数之后可以减少碰撞。**

所谓 **“拉链法”** 就是：将链表和数组相结合。也就是说创建一个链表数组，数组中每一格就是一个链表。若遇到哈希冲突，则将冲突的值加到链表中即可。

JDK1.8 之后在解决哈希冲突时有了较大的变化，当链表长度大于阈值（默认为 8）（将链表转换成红黑树前会判断，如果当前数组的长度小于 64，那么会选择先进行数组扩容，而不是转换为红黑树）时，将链表转化为红黑树，以减少搜索时间。

JDK1.7采用头插法，JDK1.8采用尾插法。

### **HashMap的长度为什么是2的幂次方**

- 通过将Key的hash值与length-1进行&运算，实现了当前Key的定位，2的幂次方可以<font color="red">减少冲突（碰撞）的次数</font>，提高HashMap查询效率

- 如果length为2的次幂 ,则length-1 转化为二进制必定是11111……的形式，在与hashCode的二进制与操作效率会非常的快，而且<font color="red">空间不浪费</font>；如果length不是2的次幂，比如length为15，则length-1为14，对应的二进制为1110，在于h与操作，最后一位都为0，而0001，0011，0101，1001，1011，0111，1101这几个位置永远都不能存放元素了，空间浪费相当大，更糟的是这种情况中，数组可以使用的位置比数组长度小了很多，这意味着进一步<font color="red">增加了碰撞的几率</font>，减慢了查询的效率！这样就会造成空间的浪费。

### **ConcurrentHashMap和Hashtable的区别？**

ConcurrentHashMap结合了HashMap和HashTable二者的优势。HashMap<font color="red">没有考虑同步</font>，hashtable<font color="red">考虑了同步</font>的问题。但是hashtable<font color="red">在每次同步执行时都要锁住整个结构</font>。 ConcurrentHashMap锁的方式是稍微细粒度的。 ConcurrentHashMap将hash表分为16个桶（默认值），诸如get,put,remove等常用操作只锁当前需要用到的桶。

### **ConcurrentHashMap的具体实现**

- 该类包含两个静态内部类HashEntry和Segment；前者用来封装映射表的键值对，后者用来充当锁的角色；

- Segment是一种可重入的锁ReentrantLock，每个Segment守护一个HashEntry数组里得元素，当对HashEntry数组的数据进行修改时，必须首先获得对应的Segment锁。

### **Comparable接口和Comparator接口有什么区别**

- 前者简单，但是如果需要重新定义比较类型时，需要修改源代码。

- 后者不需要修改源代码，自定义一个比较器，实现自定义的比较方法。

### 快速失败机制(fail-fast)

是java集合的一种错误检测机制，当多个线程对集合进行<font color="red">结构上的改变</font>的操作时，有可能会产生fail-fast机制。

**例如**：假设存在两个线程（线程1、线程2），线程1通过Iterator在遍历集合A中的元素，在某个时候线程2修改了集合A的结构（是结构上面的修改，而不是简单的修改集合元素的内容），那么这个时候程序就会抛出 ConcurrentModificationException 异常，从而产生fail-fast机制。

原因：迭代器在遍历时直接访问集合中的内容，并且在遍历过程中<font color="red">使用一个 modCount 变量</font>。集合在被遍历期间如果内容发生变化，就会改变modCount的值。每当迭代器使用hashNext()/next()遍历下一个元素之前，都会检测modCount变量是否为expectedmodCount值，是的话就返回遍历；否则抛出异常，终止遍历。

**解决办法：**

1. 在遍历过程中，所有涉及到改变modCount值的地方全部加上synchronized。(加锁)
2. 使用CopyOnWriteArrayList来替换ArrayList

### HashSet

- 数据结构是哈希表。线程是非同步的。

- 保证元素唯一性的原理：判断元素的hashCode值是否相同。如果相同，还会继续判断元素的equals方法，是否为true。

### TreeSet

#### 特点

- 可以对Set集合中的元素进行排序.

- 底层数据结构是二叉树。

- 保证元素唯一性的依据：`compareTo`方法return 0。

#### 排序方式

- TreeSet排序的第一种方式：让元素自身具备比较性。
  步骤：将add进TreeSet中的元素实现Comparable接口，并且覆盖`compareTo`方法。这种顺序也是元素的自然顺序，或者叫做默认顺序。

- TreeSet的第二种排序方式。当元素自身不具备比较性时，或者具备的比较性不是所需要的。这时就需要让集合自身具备比较性（即利用其另一种构造函数建立对象）。在集合初始化时，就有了比较方式。

  步骤：利用某个指定类实现Comparator接口，并且覆盖`compare()`方法，则此类会成为一个具备比较方法的类。在建立TreeSet的时候，将此类对象传入其中.



## 多线程

### **如何指定多个线程的执行顺序**

1. 设定一个orderNum，每个线程执行结束之后，更新orderNum，指明下一个要执行的线程。并且唤醒所有的等待线程。
2. 在每一个线程的开始，要while判断orderNum是否等于自己的要求值！！不是，则wait，是则执行本线程。

### **线程和进程的区别**

1. 进程是一个“执行中的程序”，是系统<font color="red">进行资源分配和调度</font>的一个独立单位。
2. 线程是进程的一个**实体**，一个进程中拥有多个线程，线程之间共享地址空间和其它资源（所以通信和同步等操作线程比进程更加容易）
3. 线程上下文的切换比进程<font color="red">上下文切换</font>要快很多。

（1）进程切换时，涉及到当前进程的<font color="red">CPU环境的保存</font>和新被调度运行进程的<font color="red">CPU环境的设置</font>。

（2）线程切换仅需要保存和设置少量的<font color="red">寄存器</font>内容，<font color="red">不涉及存储管理方面</font>的操作。

