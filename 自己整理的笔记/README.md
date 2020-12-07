- [计算机网络](#计算机网络)
  - [7层结构](#7层结构)
  - [输入网址后发生了什么](#输入网址后发生了什么)
  - [为什么DNS用udp](#为什么dns用udp)
  - [网络协议为什么分层](#网络协议为什么分层)
  - [什么是TCP/IP协议](#什么是tcpip协议)
  - [TCP的定义](#tcp的定义)
  - [TCP头部格式](#tcp头部格式)
  - [UDP头部格式](#udp头部格式)
  - [TCP粘包（没写完）](#tcp粘包没写完)
  - [TCP三次握手](#tcp三次握手)
  - [三次握手报文丢失问题](#三次握手报文丢失问题)
  - [三次握手初始序列号](#三次握手初始序列号)
    - [TCP序列号预测攻击原理（没写）](#tcp序列号预测攻击原理没写)
  - [TCP为什么是三次握手](#tcp为什么是三次握手)
  - [四次挥手过程](#四次挥手过程)
  - [为什么客户端关闭连接前要等待2MSL时间？](#为什么客户端关闭连接前要等待2msl时间)
  - [为什么挥手需要四次](#为什么挥手需要四次)
  - [挥手一定需要四次吗？](#挥手一定需要四次吗)
  - [TIME_WAIT状态（没写）](#time_wait状态没写)
  - [SYN Cookies](#syn-cookies)
  - [服务器主动中断](#服务器主动中断)
  - [为什么还需要快速重传机制](#为什么还需要快速重传机制)
  - [拥塞控制](#拥塞控制)
  - [tcp慢开始，为什么指数级别还叫慢开始](#tcp慢开始为什么指数级别还叫慢开始)
  - [流量控制（没写）](#流量控制没写)
  - [TCP快速建立连接](#tcp快速建立连接)
  - [TCP和UDP的区别](#tcp和udp的区别)
  - [TCP确保传输可靠性的方式](#tcp确保传输可靠性的方式)
  - [有一个 IP 的服务器监听了一个端口，它的 TCP 的最大连接数是多少？](#有一个-ip-的服务器监听了一个端口它的-tcp-的最大连接数是多少)
  - [TCP半连接和全连接队列（这个没弄懂）](#tcp半连接和全连接队列这个没弄懂)
  - [TCP Socket编程](#tcp-socket编程)
  - [TCP，UDP数据包大小的限制](#tcpudp数据包大小的限制)
  - [BBR（这个还需要了解）](#bbr这个还需要了解)
  - [快速重传解决的问题](#快速重传解决的问题)
  - [糊涂窗口综合症](#糊涂窗口综合症)
  - [tcp异常(没写)](#tcp异常没写)
- [Java](#java)
  - [JRE和JDK的区别](#jre和jdk的区别)
  - [基本数据类型](#基本数据类型)
  - [Math.round(11.5) 等于多少?Math.round(-11.5)等于多少](#mathround115-等于多少mathround-115等于多少)
  - [访问修饰符](#访问修饰符)
  - [final finally finalize区别](#final-finally-finalize区别)
  - [面向对象的三大特性](#面向对象的三大特性)
  - [类的实例化顺序](#类的实例化顺序)
  - [Java创建对象的5种方式](#java创建对象的5种方式)
  - [抽象类和接口的区别](#抽象类和接口的区别)
  - [方法多态的实现](#方法多态的实现)
  - [内部类](#内部类)
  - [重载与重写的区别](#重载与重写的区别)
  - [==和equals的区别](#和equals的区别)
  - [hashCode（）与equals（）的相关规定](#hashcode与equals的相关规定)
  - [Integer a= 127 与 Integer b = 127相等吗](#integer-a-127-与-integer-b--127相等吗)
  - [Object类方法](#object类方法)
  - [String有关](#string有关)
    - [结构演变](#结构演变)
    - [创建方式](#创建方式)
    - [不可变性](#不可变性)
    - [拼接字符串的优化](#拼接字符串的优化)
    - [常用方法](#常用方法)
    - [intern()方法(还没写)](#intern方法还没写)
  - [异常](#异常)
    - [try-catch-finally-return执行顺序](#try-catch-finally-return执行顺序)
  - [反射](#反射)
  - [动态代理（没看懂）](#动态代理没看懂)
  - [CGLIB和JDK](#cglib和jdk)
  - [BIO,NIO,AIO有什么区别？](#bionioaio有什么区别)
  - [Java8新特性](#java8新特性)
    - [接口内允许添加默认实现的方法](#接口内允许添加默认实现的方法)
    - [Lambda表达式](#lambda表达式)
    - [内置函数式接口](#内置函数式接口)
    - [Optional](#optional)
    - [Stream流](#stream流)
  - [集合](#集合)
    - [集合框架底层数据结构](#集合框架底层数据结构)
    - [fail-fast机制](#fail-fast机制)
    - [comparable 和 comparator的区别？](#comparable-和-comparator的区别)
    - [List和Set的区别](#list和set的区别)
    - [ArrayList的优缺点](#arraylist的优缺点)
    - [Arrays.asList为什么不能增加或修改](#arraysaslist为什么不能增加或修改)
    - [ArrayList和LinkedList的区别](#arraylist和linkedlist的区别)
    - [ArrayList和Vector的区别](#arraylist和vector的区别)
    - [为什么ArrayList的elementData要加上transient修饰](#为什么arraylist的elementdata要加上transient修饰)
    - [HashSet的实现原理](#hashset的实现原理)
    - [HashSet如何检查重复](#hashset如何检查重复)
    - [hashmap1.7和1.8的区别](#hashmap17和18的区别)
    - [为什么扩容的时候一定必须是2的多少次幂](#为什么扩容的时候一定必须是2的多少次幂)
    - [为什么JDK1.7的时候是先进行扩容后进行插入，而JDK1.8的时候是先插入后扩容](#为什么jdk17的时候是先进行扩容后进行插入而jdk18的时候是先插入后扩容)
    - [为什么在JDK1.8中进行hashmap优化时，把链表转化为红黑树的阈值是8，而不是7或20呢？](#为什么在jdk18中进行hashmap优化时把链表转化为红黑树的阈值是8而不是7或20呢)
    - [哈希表如何解决Hash冲突](#哈希表如何解决hash冲突)
    - [为什么hashmap具备下述特点：键-值(key-value)都允许为空，线程不安全，不保证有序，存储位置随时间变化](#为什么hashmap具备下述特点键-值key-value都允许为空线程不安全不保证有序存储位置随时间变化)
    - [为什么HashMap中String,Integer这样的包装类适合作为key键](#为什么hashmap中stringinteger这样的包装类适合作为key键)
    - [HashMap中的key若Object类型，则需实现哪些方法?](#hashmap中的key若object类型则需实现哪些方法)
    - [Hashmap1.7和1.8扩容机制对比](#hashmap17和18扩容机制对比)
    - [hashmap put方法流程](#hashmap-put方法流程)
    - [为什么头插法会产生死循环](#为什么头插法会产生死循环)
    - [HashMap与HashTable的区别](#hashmap与hashtable的区别)
    - [TreeMap](#treemap)
    - [如何决定使用 HashMap 还是 TreeMap？](#如何决定使用-hashmap-还是-treemap)
    - [HashMap 和 ConcurrentHashMap 的区别](#hashmap-和-concurrenthashmap-的区别)
    - [ConcurrentHashMap 基本结构](#concurrenthashmap-基本结构)
    - [ConcurrentHashMap put方法流程](#concurrenthashmap-put方法流程)
    - [ConcurrentHashMap 扩容流程（还没写）](#concurrenthashmap-扩容流程还没写)
    - [ConcurrentHashMap为什么不能存值为null的value（主要学习作者的学习方式）](#concurrenthashmap为什么不能存值为null的value主要学习作者的学习方式)
  - [阻塞队列(BlockingQueue）](#阻塞队列blockingqueue)
    - [LinkedBlockingQueue和ArrayBlockingQueue（没写完）](#linkedblockingqueue和arrayblockingqueue没写完)
  - [生产者消费者模式的实现（还没写）](#生产者消费者模式的实现还没写)
  - [创建线程的三种方式](#创建线程的三种方式)
  - [线程状态转换关系](#线程状态转换关系)
  - [sleep()和wait()的区别](#sleep和wait的区别)
  - [volatile(还没写)](#volatile还没写)
  - [多线程8锁](#多线程8锁)
    - [公平锁/非公平锁](#公平锁非公平锁)
    - [可重入锁](#可重入锁)
    - [独享锁/共享锁](#独享锁共享锁)
    - [互斥锁/读写锁](#互斥锁读写锁)
    - [乐观锁/悲观锁](#乐观锁悲观锁)
    - [分段锁](#分段锁)
    - [偏向锁/轻量级锁/重量级锁](#偏向锁轻量级锁重量级锁)
    - [自旋锁](#自旋锁)
  - [锁机制（b站那个视频没总结完）](#锁机制b站那个视频没总结完)
  - [为什么synchronized无法禁止指令重排，却能保证有序性？](#为什么synchronized无法禁止指令重排却能保证有序性)
  - [线程池](#线程池)
    - [参数](#参数)
    - [四种拒绝策略](#四种拒绝策略)
    - [工作流程](#工作流程)
    - [如何实现线程复用](#如何实现线程复用)
  - [CountDownLatch,CyclicBarrier,Semaphore(没写完)](#countdownlatchcyclicbarriersemaphore没写完)
  - [AQS（没写完）](#aqs没写完)
    - [获取锁](#获取锁)
  - [JDBC流程](#jdbc流程)
- [JVM](#jvm)
  - [四种引用](#四种引用)
    - [虚引用](#虚引用)
  - [TLAB分配](#tlab分配)
  - [为什么用元空间](#为什么用元空间)
  - [类加载过程](#类加载过程)
  - [对象从年轻代进入老年代的时机](#对象从年轻代进入老年代的时机)
  - [触发Full GC的时机](#触发full-gc的时机)
  - [Minor GC的触发条件](#minor-gc的触发条件)
  - [“无用的类”的判断条件](#无用的类的判断条件)
  - [如何判断一个常量是废弃常量](#如何判断一个常量是废弃常量)
  - [双亲委派机制](#双亲委派机制)
  - [全盘负责](#全盘负责)
  - [并发标记](#并发标记)
  - [G1收集器原理](#g1收集器原理)
  - [常量池](#常量池)
  - [保守和非保守GC](#保守和非保守gc)
- [算法题](#算法题)
  - [只出现一次的数字(136)](#只出现一次的数字136)

# 计算机网络

## 7层结构

自底向上分别是:

- 物理层：负责透明传输比特流
- 数据链路层：负责将网络层传下来的IP数据报组装成帧，检测和校正物理层传输介质上产生的传输差错，具体的有PPP，STP
- 网络层：负责为不同主机提供通信服务，网络层的分组数据从源端传到目的端，具体协议有IP,ARP,RARP,ICMP,IGMP等
- 传输层：负责为不同主机中的进程提供通信服务，具体协议有TCP，UDP
- 会话层：允许不同主机上各进程之间的会话
- 表示层：处理在两个通信系统中交换信息的表示方式
- 应用层：为特殊类型的网络应用提供OSI环境手段

## 输入网址后发生了什么

1.解析URL，确定Web服务器和文件名

2.查询服务器域名对应的IP地址：首先查找浏览器上缓存，没有再查找.host文件的缓存，如果没有会发送一个DNS请求给本地DNS域名服务器，本地域名服务器收到请求后如果缓存中的表格能找到则直接返回IP地址，如果没有，则去问根域名服务器。根DNS收到本地DNS的请求后，发现后置是.com。根域名服务器返回本地域名服务器.com顶级域名服务器的地址，本地DNS再去问顶级域名服务器，顶级域名服务器地址告诉本地DNS权威DNS服务器地址，本地DNS再去问就拿到IP地址了。

3.协议栈进行TCP三次握手。TCP模块在执行各阶段操作时，都需要委托IP模块将数据封装成网络包发送给通信对象，接下来网络包在IP头部的前面加上MAC头部（网卡驱动从IP模块获取到包后，将其复制到网卡内的缓存区中，并加上报头和起始帧分界符，在末尾加上用于检测错误的帧校验序列），网卡将数字信号转换为电信号进行传输，接下来包通过交换机原样转发到目的地，之后到达路由器，并在此被转发到下一个路由器或目标设备。

4.数据包抵达服务器之后，服务器会先查看数据包的MAC头部，查看是否和服务器自己的MAC地址符合，接着继续查看数据包的IP头，发现IP地址符合，根据IP头中的协议项，知道自己上层是TCP协议，接下来查看TCP头部中的序列号，如果是想要的，就放入缓存中然后返回一个ACK，如果不是就丢弃。服务器再根据TCP头部中的端口号，将包发给HTTP进程，最后浏览器获得数据后进行渲染。

## 为什么DNS用udp

https://www.zhihu.com/question/310145373

采用TCP传输，则域名解析时间为：

DNS域名解析时间 = TCP连接时间 + DNS交易时间

采用UDP传输，则域名解析时间为：

DNS域名解析时间 = DNS交易时间

很显然，采用UDP传输，DNS域名解析时间更小。

在很多时候，用户在访问一些冷门网站时，由于DNS服务器没有冷门网站的解析缓存，需要到域名根服务器、一级域名服务器、二级域名服务器迭代查询，直到查询到冷门网站的权威服务器，这中间可能涉及到多次的查询。

如果使用TCP传输，多几次查询，就多几次TCP连接时间，这多出来的时间不容小觑

## 网络协议为什么分层

(1)各层之间是独立的。上一层的工作如何进行并不影响下一层的工作，这样我们在进行每一层的工作[设计](https://www.applysquare.com/fos-cn/design/)时只要保证接口不变可以随意调整层内的工作方式。

(2)灵活性好。当任何一层发生变化时，只要层间接口关系保持不变，则在这层以上或以下各层均不受影响。当某一层出现技术革新或者某一层在工作中出现问题时不会连累到其他层的工作，排除问题时也只需要考虑这一层单独的问题即可。

(3)结构上可分割开。各层都可以采用最合适的技术来实现。技术的发展往往是不对称的，层次化的划分有效避免了木桶效应，不会因为某一方面技术的不完善而影响整体的工作效率。

(4)易于实现和维护。这种结构使得实现和调试一个庞大又复杂的系统变得易于处理，因为整个的系统已被分解为若干个相对独立的子系统。进行调试和维护时，可以对每一层进行单独的调试，避免了出现找不到问题、解决错问题的情况。

(5)能促进标准化工作。因为每一层的功能及其所提供的服务都已有了精确的说明。标准化的好处就是可以随意替换其中的某几层，对于使用和科研来说十分方便。

## 什么是TCP/IP协议

TCP/IP协议是指一个由[FTP](https://baike.baidu.com/item/FTP/13839)、[SMTP](https://baike.baidu.com/item/SMTP/175887)、TCP、[UDP](https://baike.baidu.com/item/UDP/571511)、IP等协议构成的协议簇。只是因为在TCP/IP协议中TCP协议和IP协议最具代表性，所以被称为TCP/IP协议。TCP/IP传输协议，即传输控制/网络协议，也叫作网络通讯协议。TCP/IP传输协议是严格来说是一个四层的体系结构，应用层、传输层、网络层和数据链路层都包含其中。

## TCP的定义

TCP协议是面向连接的、可靠的、基于字节流的传输层通信协议。

面向连接：使用TCP传输数据前，必须先建立TCP连接；传输完成后再释放连接。

全双工通信:建立TCP连接后，通信双方都能发送数据

可靠：通过TCP连接传送的数据，不丢失，无差错，不重复&&按序到达

面向字节流：数据以流的形式进行传输，TCP一次传输的报文长度有限制，若太大则需分块，分次传输，但由于TCP连接的可靠性，接收方可按顺序接收数据块&重新组成分块之前的数据流，所以TCP看起来就像直接互相传输字节流一样。

## TCP头部格式

主要使用的几个选项：

SYN(synchronous)： 发送/同步标志，用来建立连接，和下面的第二个标志位ACK搭配使用。连接开始时，SYN=1，ACK=0，代表连接开始但是未获得响应。当连接被响应的时候，标志位会发生变化，其中ACK会置为1，代表确认收到连接请求，此时的标志位变成了 SYN=1，ACK=1。

ACK(acknowledgement)：确认标志，表示确认收到请求。

PSH(push) ：表示推送操作，就是指数据包到达接收端以后，不对其进行队列处理，而是尽可能的将数据交给应用程序处理；

FIN(finish)：结束标志，用于结束一个TCP会话；

RST(reset)：重置复位标志，用于复位对应的TCP连接。

URG(urgent)：紧急标志，用于保证TCP连接不被中断，并且督促中间层设备尽快处理。

## UDP头部格式

- 16位源端口号
- 16位目标端口号
- 16位包长度
- 16位校验和
- 数据

## TCP粘包（没写完）

TCP 是一个面向字节流的协议，它是性质是流式的，所以它并没有分段。就像水流一样，你没法知道什么时候开始，什么时候结束。

![](https://user-gold-cdn.xitu.io/2018/8/6/1650c8b818748287?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

接收到的是一个报文，它是由发送的两个报文组成的，这样称为粘包。

解决方式：

- 在报文末尾增加换行符表明一条完整的消息，这样在接收端可以根据这个换行符来判断消息是否完整。
- 将消息分为消息头、消息体。可以在消息头中声明消息的长度，根据这个长度来获取报文（比如 808 协议）。
- 规定好报文长度，不足的空位补齐，取的时候按照长度截取即可。

## TCP三次握手

建立TCP连接前：TCP客户端，服务端都处于关闭状态（CLOSED），直到客户端主动打开连接，服务端才被动打开连接（处于监听状态LISTEN）,等待接收客户端的请求。

第一次握手时，客户端向服务器发送1个连接请求的报文段，此报文段同步标志位SYN=1，随机选择一个起始序号seq=x，不携带数据，客户端进入同步已发送状态（SYN_SEND），等待服务器确认。

第二次握手时，服务器收到请求连接的报文段后，若同意建立连接，则向客户端发送连接确认的报文段，该报文段的同步标志位SYN=1，确认标记位ACK=1，随机选择一个起始序号seq=y，确认号字段ack=x+1，不携带数据，服务器进入同步已接收状态（SYN_RCVD）

第三次握手，客户端收到确认报文段后，向服务器再次发出连接确认报文段，该报文段的确认标记位ACK=1，序号seq=x+1，确认号字段ack=y+1，可以携带数据，客户端和服务器端都进入已创建状态(ESTABLISHED)

## 三次握手报文丢失问题

第一次握手丢失：

每次超时时间RTO是指数(翻倍)上涨的，当超过最大重传次数后，客户端不再发送SYN包。在Linux中，第一次握手的SYN超时重传次数，是如下内核参数指定的:

`cat /proc/sys/net/ipv4/tcp_syn_retries`,默认值为5，也就是SYN最大重传次数是5次。

第二次握手丢失：

当第二次握手的SYN，ACK丢包时，客户端会超时重发SYN包，服务端也会超时重传SYN，ACK包。

第三次握手：

在建立TCP连接时，如果第三次握手的ACK，服务端无法收到，则服务端就会短暂处于`SYN_RECV`状态，而客户端会处于`ESTABLISHED	`状态.

由于服务端一直收不到TCP第三次握手的ACK，则会一直重传SYN,ACK包，直到重传次数超过`tcp_synack_retries`值（默认值5次）后,服务端就会断开TCP连接。

而客户端则会有两种情况:

- 如果客户端没发送数据包,一直处于`ESTABLISHED`状态，然后经过2小时11分15秒才可以发现一个死亡连接，于是客户端连接就会断开连接。
- 如果客户端发送了数据包，一直没有收到服务端对该数据包的确认报文，则会一直重传该数据包，直到重传次数超过`tcp_retries2`值（默认值15次）后，客户端就会断开TCP连接

## 三次握手初始序列号

大约每4微秒增加1，为了防止序列号猜测攻击

### TCP序列号预测攻击原理（没写）

## TCP为什么是三次握手

主要有三方面的原因：
1.避免历史连接：

客户端连续发送多次SYN建立连接的报文，在网络拥堵等情况下：一个旧SYN报文比最新的SYN报文早到达了客户端,此时服务端就会回一个`SYN+ACK`报文给客户端，客户端收到后可以根据自身的上下文，判断这是否是一个历史连接（序列号过期或超时）。如果是历史连接，则第三次握手发送的报文是RST报文，以此中止历史连接，如果不是历史连接，则第三次发送的报文是`ACK`报文，通信双方就会成功建立连接。如果是两次握手连接，就不能判断当前连接是否是历史连接。

2.同步双方初始序列号：

当客户端发送携带「初始序列号」的 `SYN` 报文的时候，需要服务端回一个 `ACK` 应答报文，表示客户端的 SYN 报文已被服务端成功接收，那当服务端发送「初始序列号」给客户端的时候，依然也要得到客户端的应答回应，**这样一来一回，才能确保双方的初始序列号能被可靠的同步。**

3.避免资源浪费：

如果客户端的 `SYN` 阻塞了，重复发送多次 `SYN` 报文，那么服务器在收到请求后就会**建立多个冗余的无效链接，造成不必要的资源浪费。**

「四次握手」：三次握手就已经理论上最少可靠连接建立，所以不需要使用更多的通信次数。

## 四次挥手过程

释放TCP连接前，TCP客户端和服务器都处于已创建状态(ESTABLISHED)直到客户端主动关闭TCP连接。

第一次挥手时，客户端向服务器发送1个连接释放的报文段，该报文段终止控制位FIN=1，报文段序号为前面传送数据最后1个字节的序号加1，可以携带数据，客户端进入终止等待1状态（FIN-WAIT-1），等待服务器确认。

第二次挥手时，服务器收到连接释放报文段后，则向客户端发回连接释放确认的报文段，该报文段确认标记位ACK=1，报文段序号seq为前面传送数据最后一个字节的序号加1：seq=v，确认号字段设为ack=u+1，此时服务器进入关闭等待状态（CLOSE-WAIT），客户端收到服务器的确认后，进入终止等待2状态(FIN-WAIT-2),等待服务器发出释放连接请求，至此，客户端到服务器的TCP连接已断开，即TCP连接处于半关闭状态，即客户端到服务器的连接断开，服务器到客户端的连接未断开。

第三次挥手时，若服务器已无数据要向客户端发送，则发出释放连接的报文段，该报文段终止控制位FIN=1，确认标记位ACK=1，报文段序号seq=w，重复上次已发送的确认号字段ack=u+1，可以携带数据，服务端进入最后确认状态（LAST-ACK）

第四次挥手时，客户端收到连接释放报文段后，则向服务器发回连接释放确认的报文段，该报文段确认标记位ACK=1，报文段序号seq=u+1，确认号字段ack=w+1，可以携带数据（？），客户端进入时间等待状态（TIME_WAIT），服务器进入关闭状态（CLOSED），此时TCP连接还未释放，须经过时间等待计时器设置的时间2MSL后，客户端才进入连接关闭状态(CLOSED)

## 为什么客户端关闭连接前要等待2MSL时间？

原因1：为了保证客户端发送的最后1个连接释放确认报文能到达服务器，从而使得服务器能正常释放连接。

原因2：防止上文提到的早已失效的连接请求报文出现在本连接中，客户端发送了最后1个连接释放请求确认报文后，再经过2MSL时间，则可使本连接持续时间内所产生的所有报文段都从网络中消失，即在下一个新的连接中就不会出现早已失效的连接请求报文。

## 为什么挥手需要四次

- 关闭连接时，客户端向服务端发送 `FIN` 时，仅仅表示客户端不再发送数据了但是还能接收数据。
- 服务器收到客户端的`FIN`报文时，先回一个`ACK`应答报文，而服务端可能还有数据需要处理和发送，等服务端不再发送数据时，才发送`FIN`报文给客户端来表示同意现在关闭连接。

从上面过程可知，服务端通常需要等待完成数据的发送和处理，所以服务端的`ACK`和`FIN`一般都会分开发送，从而比三次握手导致多了一次。

## 挥手一定需要四次吗？

假设client已经没有数据发送给server了，所以它发送FIN给server表明自己数据发完了，不再发了，如果这时候server还是有数据要发送给client,那么它就是先回复ack，然后继续发送数据。

等server数据发送完了之后再向client发送FIN表明它也发完了，然后等client的ACK这种情况下就会有四次挥手。

那么假设client发送FIN给server的时候server也没数据给client,那么server就可以将ACK和它的FIN一起发给client,然后等待client的ACK，这样不就三次挥手了?

## TIME_WAIT状态（没写）

## SYN Cookies

是用来防范SYN Flood攻击的一种手段。

SYN Flood攻击是指攻击者在短时间内发送大量的TCP SYN包给受害者。受害者(服务器)为每个TCP SYN包分配一个特定的数据区，只要这些SYN包具有不同的源地址(攻击者很容易伪造)。这将给TCP服务器造成很大的系统负担，最终导致系统不能正常工作。

SYN Cookie的原理是在TCP服务器接收到TCP SYN包并返回TCP SYN+ACK包时，不分配一个专门的数据区，而是根据这个SYN包计算出一个cookie值。这个cookie作为将要返回的SYN ACK包的初始序列号。当客户端返回一个ACK包时，根据包头信息计算cookie，与返回的确认序列号（初始序列号+1）进行对比，如果相同，则是一个正常连接，然后分配资源，建立连接。

cookie的计算:服务器收到一个SYN包,计算一个消息摘要mac.

## 服务器主动中断

当服务器进程被终止时，会关闭其打开的所有文件描述符，此时就会向客户端发送一个`FIN`的报文，客户端则响应一个`ACK`报文，但是这样只完成了四次挥手的前两次挥手，也就是说这样只实现了半关闭，客户端仍然可以向服务器写入数据。

但是当客户端向服务器写入数据时，由于服务器端的套接字进程已经终止，此时连接的状态已经异常了，所以服务端进程不会向客户端发送ACK报文，而是发送了一个RST报文请求将处于异常状态的连接复位， **如果客户端此时还要向服务端发送数据，将诱发服务端TCP向服务端发送SIGPIPE信号，因为向接收到RST的套接口写数据都会收到此信号.** 所以说，这就是为什么我们主动关闭服务端后，用客户端向服务端写数据，还必须是写两次后连接才会关闭的原因。

## 为什么还需要快速重传机制

超时重传是按时间来驱动的，如果是网络状况真的不好的情况，超时重传没问题，但是如果网络状况好的时候，只是恰巧丢包了，那等这么长时间就没必要。

于是又引入了数据驱动的重传叫快速重传，发送方如果连续三次收到对方相同的确认号，那么马上重传数据。

因为连续收到三次相同 ACK 证明当前网络状况是 ok 的，那么确认是丢包了，于是立马重发，没必要等这么久。

## 拥塞控制

**过程解析**:

阶段1:因cwnd<ssthresh，使用慢开始算法

阶段2：因cwnd>ssthresh,故停止使用慢开始算法而改用拥塞避免算法

阶段3：出现网络拥塞，把慢开始门限（ssthresh）设置为出现拥塞时的发送方窗口值的一半，把拥塞窗口（cwnd）重新设置为1

阶段4：因cwnd<ssthresh，故使用慢开始算法

阶段5：因cwnd>ssthresh，故停止使用慢开始算法而改用拥塞避免算法

注：

a.乘法减小：出现网络拥塞时慢开始门限设置为出现拥塞时的发送方窗口值的一半

b.加法增大：拥塞避免时的缓慢增大

c.二者合并叫为AIMD算法（即加法增大，乘法减少）

目的是为了防止过多的数据注入到网络中。

## tcp慢开始，为什么指数级别还叫慢开始

虽然窗口是指数增加，但是相比于一开始就选择大窗口，仍然较慢

## 流量控制（没写）

## TCP快速建立连接

![](https://mmbiz.qpic.cn/mmbiz_png/J0g14CUwaZctmf3ObkESj41ayTbgy9q4ThRjO0ukiaIPYKAsY8XThOp0f1R4Id6L9icUxj7GUvLica7hmfB9DibG9g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

- 在第一次建立连接的时候，服务端在第二次握手产生一个cookie(已加密)并通过SYN、ACK包一起发给客户端，于是客户端就会缓存这个cookie，所以第一次发起HTTP Get请求的时候，还是需要2个RTT的时延
- 在下次请求的时候，客户端在SYN包带上cookie发给服务端，就提前可以跳过三次握手的过程，因为Cookie中维护了一些信息，服务端可以从Cookie获取TCP相关的信息，这时发起的HTTP GET请求就只需要1个RTT的时延

## TCP和UDP的区别

- TCP是面向连接的，UDP是面向报文的
- TCP传输可靠，UDP传输不可靠
- TCP的传输形式是字节流，UDP的传输形式是数据报文段
- TCP传输效率较慢，UDP传输效率快
- TCP需要的资源多，UDP所需资源少
- TCP主要应用于要求通信数据可靠的场景，UDP主要应用于要求通信速度高的场景

- TCP首部字节为20-60个字节，UDP首部字节为8个字节
- UDP不存在发送缓存

[^什么是short write]: 对于一个非阻塞的TCP套接口，如果其发送缓冲区中根本没有空间，输出函数调用将立即返回一个EWOULDBLOCK错误。如果其发送缓冲区中有一些空间，返回值将是内核能够拷贝到该缓冲区中的字节数。这个字节数也称为不足计数(应该就是short write的意思)

## TCP确保传输可靠性的方式

TCP协议保证数据传输可靠性的方式主要有:

- 校验和
- 序列号**用来解决网络包乱序问题**

接收方可以去除重复的数据；

接收方可以根据数据包的序列号按序接收；

可以标识发送出去的数据包中，哪些是已经被对方收到的：

- 确认应答**用来解决不丢包的问题**
- 超时重传
- 连接管理
- 流量控制
- 拥塞控制

## 有一个 IP 的服务器监听了一个端口，它的 TCP 的最大连接数是多少？

理论值计算公式如下：最大TCP连接数=客户端的IP数X客户端的端口数

对IPv4，客户端的IP数最多为2的32次方，客户端的端口数最多为2的16次方，也就是服务端单机最大TCP连接数，约为2的48次方。

当然，服务端最大并发 TCP 连接数远不能达到理论上限。

- 首先主要是**文件描述符限制**，Socket 都是文件，所以首先要通过 `ulimit` 配置文件描述符的数目；
- 另一个是**内存限制**，每个 TCP 连接都要占用一定内存，操作系统是有限的。

## TCP半连接和全连接队列（这个没弄懂）

![半连接队列与全连接队列](https://cdn.jsdelivr.net/gh/xiaolincoder/ImageHost/计算机网络/TCP-半连接和全连接/3.jpg)

- 0 ：如果全连接队列满了，那么 server 扔掉 client 发过来的 ack ；
- 1 ：如果全连接队列满了，server 发送一个 `reset` 包给 client，表示废掉这个握手过程和这个连接；

只要服务器没有为请求回复 ACK，请求就会被多次**重发**。如果服务器上的进程只是**短暂的繁忙造成 accept 队列满，那么当 TCP 全连接队列有空位时，再次接收到的请求报文由于含有 ACK，仍然会触发服务器端成功建立连接。**

## TCP Socket编程

- 服务端和客户端初始化 `socket`，得到文件描述符；
- 服务端调用 `bind`，将绑定在 IP 地址和端口;
- 服务端调用 `listen`，进行监听；
- 服务端调用 `accept`，等待客户端连接；
- 客户端调用 `connect`，向服务器端的地址和端口发起连接请求；
- 服务端 `accept` 返回用于传输的 `socket` 的文件描述符；
- 客户端调用 `write` 写入数据；服务端调用 `read` 读取数据；
- 客户端断开连接时，会调用 `close`，那么服务端 `read` 读取数据的时候，就会读取到了 `EOF`，待处理完数据后，服务端调用 `close`，表示连接关闭。

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/0_1314694589UeXT.gif)

## TCP，UDP数据包大小的限制

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/image-20200813111620210.png)

我们从下到上分析一下： 　　
1.在链路层，由以太网的物理特性决定了数据帧的长度为(46＋18)－(1500＋18)，其中的18是数据帧的头和尾，也就是说数据帧的内容最大为1500(不包括帧头和帧尾)，即MTU(Maximum Transmission Unit)为1500； 　
2.在网络层，因为IP包的首部要占用20字节，所以这的MTU为1500－20＝1480；　
3.在传输层，对于UDP包的首部要占用8字节，所以这的MTU为1480－8＝1472； 　　
所以，在应用层，你的Data最大长度为1472。当我们的UDP包中的数据多于MTU(1472)时，发送方的IP层需要分片fragmentation进行传输，而在接收方IP层则需要进行数据报重组，由于UDP是不可靠的传输协议，如果分片丢失导致重组失败，将导致UDP数据包被丢弃。 　　
从上面的分析来看，在普通的局域网环境下，UDP的数据最大为1472字节最好(避免分片重组)。

UDP 包的大小就应该是 1500 - IP头(20) - UDP头(8) = 1472(Bytes)
TCP 包的大小就应该是 1500 - IP头(20) - TCP头(20) = 1460 (Bytes)

## BBR（这个还需要了解）

BBR算法是个主动的闭环反馈系统，通俗来说就是根据带宽和RTT延时来不断动态探索寻找合适的发送速率和发送量。

## 快速重传解决的问题

快速重传解决了超时重发的时间等待（每一次遇到超时重传时，都会将下一次超时时间间隔设为先前值的两倍）。

但是仍然面临**重传的时候，是重传之前的一个，还是重传所有的问题。**

于是又引入了：`SACK`选择性确认

这种方式需要在 TCP 头部「选项」字段里加一个 `SACK` 的东西，它**可以将缓存的地图发送给发送方**，这样发送方就可以知道哪些数据收到了，哪些数据没收到，知道了这些信息，就可以**只重传丢失的数据**。

Duplicate SACK 又称 `D-SACK`，其主要**使用了 SACK 来告诉「发送方」有哪些数据被重复接收了。**

`	D-SACK` 有这么几个好处：

1. 可以让「发送方」知道，是发出去的包丢了，还是接收方回应的 ACK 包丢了;
2. 可以知道是不是「发送方」的数据包被网络延迟了;
3. 可以知道网络中是不是把「发送方」的数据包给复制了;

## 糊涂窗口综合症

**如果接收方腾出几个字节并告诉发送方现在有几个字节的窗口，而发送方会义无反顾地发送这几个字节，这就是糊涂窗口综合症**。

要解决糊涂窗口综合症，

- 让接收方不通告小窗口给发送方
- 让发送方避免发送小数据

## tcp异常(没写)

# Java

## JRE和JDK的区别

JRE： Java Runtime Environment，java运行时环境，包含了java虚拟机，java基础类库。是使用java语言编写的程序运行所需要的软件环境，是提供给想运行java程序的用户使用的。

JDK：Java Development Kit，java开发工具包，是程序员使用java语言编写java程序所需的开发工具包，是提供给程序员使用的。JDK包含了JRE，同时还包含了编译java源码的编译器。

## 基本数据类型

![](https://user-gold-cdn.xitu.io/2020/4/14/171744c434465b69?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

## Math.round(11.5) 等于多少?Math.round(-11.5)等于多少

Math.round(11.5)的返回值是 12，Math.round(-11.5)的返回值是-11。四舍五入的原理是在参数上加 0.5 然后进行下取整。

## 访问修饰符

- private : 在同一类内可见。使用对象：变量、方法。 注意：不能修饰类（外部类）

- default (即缺省，什么也不写，不使用任何关键字）: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变量、方法。

- protected : 对同一包内的类和所有子类可见。使用对象：变量、方法。 注意：不能修饰类（外部类）。

- public : 对所有类可见。使用对象：类、接口、变量、方法

![](https://user-gold-cdn.xitu.io/2020/4/14/171744c433bcfd38?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

## final finally finalize区别

- final可以修饰类、变量、方法，修饰类表示该类不能被继承、修饰方法表示该方法不能被重写、修饰变量表 示该变量是一个常量不能被重新赋值。
- finally一般作用在try-catch代码块中，在处理异常的时候，通常我们将一定要执行的代码方法finally代码块 中，表示不管是否出现异常，该代码块都会执行，一般用来存放一些关闭资源的代码。
- finalize是一个方法，属于Object类的一个方法，而Object类是所有类的父类，该方法一般由垃圾回收器来调 用，当我们调用System.gc() 方法的时候，由垃圾回收器调用finalize()，回收垃圾，一个对象是否可回收的 最后判断。

## 面向对象的三大特性

- 封装：把一个对象的属性私有化，同时提供一些可以被外界访问的属性的方法
- 继承：使用已存在的类的定义作为基础建立新类
- 多态：父类或接口定义的引用变量可以指向子类或具体实现类的实例对象。

## 类的实例化顺序

父类静态代码块/静态域->子类静态代码块/静态域 -> 父类非静态代码块 -> 父类构造器 -> 子类非静态代码块 -> 子类构造器

## Java创建对象的5种方式

- 用new语句创建对象。

- 使用反射，使用`Class.newInstance()`创建对象/调用类对象的**构造方法**——Constructor

- 调用对象的`clone()`方法。

- 运用反序列化手段，调用`java.io.ObjectInputStream`对象的`readObject()`方法.

- 使用Unsafe

## 抽象类和接口的区别

- 定义上，抽象类是包含抽象方法的类，接口是抽象方法和全局变量的集合
- 组成上，抽象类由构造方法、抽象方法、普通方法、常量和变量构成，接口由常量、抽象方法构成，在JDK1.8之后，接口里可以有静态方法和方法体
- 使用上，子类继承抽象类，子类实现接口
- 关系上，抽象类可以实现多个接口，接口不能继承抽象类，但是允许继承多个接口
- 局限上，抽象类有单继承的局限，接口没有单继承的限制
- 声明上，抽象类使用abstract声明，接口使用interface声明

## 方法多态的实现

多态中方法多态的实现是靠动态分派。

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/image-20200801164355442.png)



虚方法表中存放着各个方法的实际入口地址。如果某个方法在子类中没有被重写，那子类的虚方法表中的地址入口和父类相同方法的地址入口是一致的，都指向父类的实现入口。如果子类中重写了这个方法，子类虚方法表中的地址也会被替换为指向子类实现版本的入口地址。

## 内部类

- 静态内部类：定义在类内部的静态类

  静态内部类可以访问外部类所有的静态变量，而不可访问外部类的非静态变量；静态内部类的创建方式，`new 外部类.静态内部类()`

- 成员内部类：定义在类内部，成员位置上的非静态类

  成员内部类可以访问外部类所有的变量和方法，包括静态和非静态，私有和公有。成员内部类依赖于外部类的实例，它的创建方式`外部类实例.new 内部类()`

- 局部内部类：定义在方法中的内部类

  定义在实例方法中的局部类可以访问外部类的所有变量和方法，定义在静态方法中的局部类只能访问外部类的静态变量和方法。局部内部类的创建方式，在对应方法内，`new 内部类()`

- 匿名内部类：没有名字的内部类

  - 匿名内部类必须继承一个抽象类或者实现一个接口。
  - 匿名内部类不能定义任何静态成员和静态方法。
  - 当所在的方法的形参需要被匿名内部类使用时，必须声明为 final。
  - 匿名内部类不能是抽象的，它必须要实现继承的类或者实现的接口的所有抽象方法。

## 重载与重写的区别

- 方法的重载和重写都是实现多态的方式，区别在于前者实现的是编译时的多态性，而后者实现的是运行时的多态性。

- 重载：发生在同一个类中，方法名相同参数列表不同（参数类型不同、个数不同、顺序不同），与方法返回值和访问修饰符无关，即重载的方法不能根据返回类型进行区分

- 重写：发生在父子类中，方法名、参数列表必须相同，返回值小于等于父类，抛出的异常小于等于父类，访问修饰符大于等于父类（里氏代换原则）；如果父类方法访问修饰符为private则子类中就不是重写。

## ==和equals的区别

**==** : 它的作用是判断两个对象的地址是不是相等。即，判断两个对象是不是同一个对象。(基本数据类型 == 比较的是值，引用数据类型 == 比较的是内存地址)

**equals()** : 它的作用也是判断两个对象是否相等。但它一般有两种使用情况：

- 情况1：类没有覆盖 equals() 方法。则通过 equals() 比较该类的两个对象时，等价于通过“==”比较这两个对象。
- 情况2：类覆盖了 equals() 方法。一般，我们都覆盖 equals() 方法来两个对象的内容相等；若它们的内容相等，则返回 true (即，认为这两个对象相等)。

## hashCode（）与equals（）的相关规定

- 如果两个对象相等，则hashcode一定也是相同的
- 两个对象相等，对两个对象分别调用equals方法都返回true
- 两个对象有相同的hashcode值，它们也不一定是相等的
- equals方法被覆盖过，则hashCode方法也必须被覆盖
- hashCode()的默认行为是对堆上的对象产生独特值。如果没有重写hashCode()，则该class的两个对象无论如何都不会相等（即使这两个对象指向相同的数据）

## Integer a= 127 与 Integer b = 127相等吗

- 对于对象引用类型：==比较的是对象的内存地址。
- 对于基本数据类型：==比较的是值。
- 如果整型字面量的值在-128到127之间，那么自动装箱时不会new新的Integer对象，而是直接引用常量池中的Integer对象，超过范围 a1==b1的结果是false

## Object类方法

- `Object()`
- `clone()`
- `equals(Object)`
- `finalize()`
- `getClass()`
- `hashCode()`
- `notify()`
- `notifyAll()`
- `toString()`
- `wait()`
- `wait(long)`
- `wait(long, int)`

## String有关

### 结构演变

![](https://user-gold-cdn.xitu.io/2019/9/23/16d5eac18d375060?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

**Java6及之前：**

是对 char 数组进行了封装实现的对象，主要有四个成员变量： char 数组、偏移量 offset、字符数量 count、哈希值 hash。通过 offset 和 count 两个属性来定位 char[] 数组，获取字符串。但这种方式很有可能会导致内存泄漏。

**Java7-8**：

占用的内存稍微少了点，同时解决了内存泄漏的问题。

**Java9:**

将char数组改为了byte数组，节约了空间。

在 Java9 维护了一个新的属性 coder，它是编码格式的标识，在计算字符串长度或者调用 indexOf() 函数时，需要根据这个字段，判断如何计算字符串长度。coder 属性默认有 0 和 1 两个值， 0 代表Latin-1（单字节编码），1 代表 UTF-16 编码。如果 `String`判断字符串只包含了 Latin-1，则 coder 属性值为 0 ，反之则为 1。

### 创建方式

- 通过字符串常量的方式：`String str = "alone"`的形式，使用这种形式创建字符串时，JVM会**在字符串常量池中先检查**是否存在该对象，如果存在，返回该对象的引用地址，如果不存在，则在字符串常量池中创建该字符串对象并且返回引用。
- 通过构造函数的方式：`String str = new String("pingtouge")`的形式，这种方式要分成两个阶段，首先在编译时，字符串`pingtouge`会被加入到常量结构中，类加载时候就会在常量池中创建该字符串。然后就是在调用new()时，JVM 将会调用`String`的构造函数，同时引用常量池中的`pingtouge`字符串， 在堆内存中创建一个`String`对象并且返回堆中的引用地址。

### 不可变性

- 因为String类用了final修饰符，所以String类不可被继承
- 用来存储字符串的`char value[]`数组被`private`和`final`修饰，不可修改`char[]`指向的地址，但是数组内的值是可以改的

### 拼接字符串的优化

当在用`+`号进行拼接字符串时，编译器会先创一个StringBuilder对象，加进去之后再转换为String.

```java
String str = "pingtouge";

for(int i=0; i<1000; i++) {
      str = str + i;
}
```

编译器会帮我们优化成:

```
String str = "pingtouge";

for(int i=0; i<1000; i++) {
        	  str = (new StringBuilder(String.valueOf(str))).append(i).toString();
}
```

### 常用方法

- `indexOf()`：返回指定字符的索引。

- `charAt()`：返回指定索引处的字符。

- `replace()`：字符串替换。

- `trim()`：去除字符串两端空白。

- `split()`：分割字符串，返回一个分割后的字符串数组。

- `getBytes()`：返回字符串的 byte 类型数组。

- `length()`：返回字符串长度。

- `toLowerCase()`：将字符串转成小写字母。

- `toUpperCase()`：将字符串转成大写字符。

- `substring()`：截取字符串。

- `equals()`：字符串比较。

### intern()方法(还没写)



## 异常

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/2019101117003396.png)

### try-catch-finally-return执行顺序

- 如果不发生异常，不会执行catch部分。

- 不管有没有发生异常，finally都会执行到。

- 即使try和catch中有return时，finally仍然会执行

- finally是在return后面的表达式运算完后再执行的。（此时并没有返回运算后的值，而是先把要返回的值保存起来，若finally中无return，则不管finally中的代码怎么样，返回的值都不会改变，仍然是之前保存的值），该情况下函数返回值是在finally执行前确定的)

- finally部分就不要return了，要不然，就回不去try或者catch的return了。

## 反射

**定义**：

动态获取的信息以及动态调用对象的方法的功能

**实现**：

jdk是通过UNSAFE类对堆内存中对象的属性进行直接的读取和写入，要读取和写入首先需要确定属性所在的位置，也就是相对对象起始位置的偏移量。

**功能**：

①、在运行时判断任意一个对象所属的类
②、在运行时构造任意一个类的对象
③、在运行时判断任意一个类所具有的成员变量和方法（通过反射设置可以调用 private）
④、在运行时调用人一个对象的方法

**缺点**

- 性能较低，JVM无法对这些代码进行优化
- 必须在没有安全限制的环境中运行
- 可移植性差

**应用场景：**

- 使用JDBC连接数据库时使用Class.forName()通过反射加载数据库的驱动程序
- Spring通过XML配置模式装载Bean：
  - 将程序内所有 XML 或 Properties 配置文件加载入内存中
  - Java类里面解析xml或properties里面的内容，得到对应实体类的字节码字符串以及相关的属性信息;
  - 使用反射机制，根据这个字符串获得某个类的Class实例;
  - 动态配置实例的属性

**获取反射的三种方法：**

- 通过new对象实现反射机制

  ```java
  //方式一(通过建立对象)
  Student stu = new Student();
  Class classobj1 = stu.getClass();
  System.out.println(classobj1.getName());
  ```

- 通过路径实现反射机制

  ```java
  //方式二（所在通过路径-相对路径）
  Class classobj2 = Class.forName("fanshe.Student");
  System.out.println(classobj2.getName());
  ```

- 通过类名实现反射机制

  ```java
  //方式三（通过类名）
  Class classobj3 = Student.class;
  System.out.println(classobj3.getName());
  ```

## 动态代理（没看懂）

https://www.zhihu.com/question/20794107

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/v2-6aacbe1e9df4fe982a68fe142401952e_720w.jpg)

## CGLIB和JDK

CGLib创建的动态代理对象性能比JDK创建的动态代理对象的性能高不少，但是CGLib在创建代理对象时所花费的时间却比JDK多得多，所以对于单例的对象，因为无需频繁创建对象，用CGLib合适，反之，使用JDK方式要更为合适一些。同时，由于CGLib由于是采用动态创建子类的方法，对于final方法，无法进行代理。

JDK动态代理在调用方法时，使用了反射技术来调用被拦截的方法，效率低下，CGLib底层采用ASM字节码生成框架，使用字节码技术生成代理类，比使用Java反射效率要高。并且CGLIB采用`fastclass`机制来进行调用，对一个类的方法建立索引，通过索引来直接调用相应的方法。唯一需要注意的是，CGLib不能对声明为final的方法进行代理。

## BIO,NIO,AIO有什么区别？

- BIO：Block IO 同步阻塞式 IO，就是我们平常使用的传统 IO，它的特点是模式简单使用方便，并发处理能力低。
- NIO：Non IO 同步非阻塞 IO，是传统 IO 的升级，客户端和服务器端通过 Channel（通道）通讯，实现了多路复用。
- AIO：Asynchronous IO 是 NIO 的升级，也叫 NIO2，实现了异步非堵塞 IO ，异步 IO 的操作基于事件和回调机制。

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

## 集合

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/20171110225615382.png)

### 集合框架底层数据结构

- Collection

  1. List
     - Arraylist： Object数组
     - Vector： Object数组
     - LinkedList： 双向循环链表

  2. Set
     - HashSet（无序，唯一）：基于 HashMap 实现的，底层采用 HashMap 来保存元素
     - LinkedHashSet： LinkedHashSet 继承与 HashSet，并且其内部是通过 LinkedHashMap 来实现的。有点类似于我们之前说的LinkedHashMap 其内部是基于 Hashmap 实现一样，不过还是有一点点区别的。
     - TreeSet（有序，唯一）： 红黑树(自平衡的排序二叉树。)

- Map
  - HashMap： JDK1.8之前HashMap由数组+链表组成的，数组是HashMap的主体，链表则是主要为了解决哈希冲突而存在的（“拉链法”解决冲突）.JDK1.8以后在解决哈希冲突时有了较大的变化，当链表长度大于阈值（默认为8）时，将链表转化为红黑树，以减少搜索时间
  - LinkedHashMap：LinkedHashMap 继承自 HashMap，所以它的底层仍然是基于拉链式散列结构即由数组和链表或红黑树组成。另外，LinkedHashMap 在上面结构的基础上，增加了一条双向链表，使得上面的结构可以保持键值对的插入顺序。同时通过对链表进行相应的操作，实现了访问顺序相关逻辑。
  - HashTable： 数组+链表组成的，数组是 HashMap 的主体，链表则是主要为了解决哈希冲突而存在的
  - TreeMap： 红黑树（自平衡的排序二叉树）

### fail-fast机制

多个线程对同一集合进行结构上的改变的操作时抛出ConcurrentModificationException 异常。

**原因：**

迭代器在遍历时直接访问集合中的内容，并且在遍历过程中使用一个 modCount 变量。集合在被遍历期间如果内容发生变化，就会改变modCount的值。每当迭代器使用hashNext()/next()遍历下一个元素之前，都会检测modCount变量是否为expectedmodCount值，是的话就返回遍历；否则抛出异常，终止遍历。

**解决方法：**

1. 在遍历过程中，所有涉及到改变modCount值得地方全部加上synchronized。
2. 使用CopyOnWriteArrayList来替换ArrayList

### comparable 和 comparator的区别？

- comparable接口实际上是出自java.lang包，它有一个 compareTo(Object obj)方法用来排序
- comparator接口实际上是出自 java.util 包，它有一个compare(Object obj1, Object obj2)方法用来排序

- 一般我们需要对一个集合使用自定义排序时，我们就要重写compareTo方法或compare方法，当我们需要对某一个集合实现两种排序方式，比如一个song对象中的歌名和歌手名分别采用一种排序方法的话，我们可以重写compareTo方法和使用自制的Comparator方法或者以两个Comparator来实现歌名排序和歌星名排序，第二种代表我们只能使用两个参数版的Collections.sort().

### List和Set的区别

- List是有序容器，Set是无序容器
- List中元素可以重复，Set中不可以存储重复元素
- List查找元素效率较高，插入删除元素效率低，Set插入和删除效率高，查找效率低
- List支持for循环遍历，Set只能用迭代器遍历

### ArrayList的优缺点

- ArrayList的优点如下：
  - ArrayList 底层以数组实现，是一种随机访问模式。ArrayList 实现了 RandomAccess 接口，因此查找的时候非常快。
  - ArrayList 在顺序添加一个元素的时候非常方便。

- ArrayList 的缺点如下：
  - 删除元素的时候，需要做一次元素复制操作。如果要复制的元素很多，那么就会比较耗费性能。
  - 插入元素的时候，也需要做一次元素复制操作，缺点同上。

- ArrayList 比较适合顺序添加、随机访问的场景。

### Arrays.asList为什么不能增加或修改

1.返回的是**内部类**，而内部类对元素的定义是final

```
private final E[] a;
```

2.Arrays继承了AbstractList<E>，而在AbstractList中U对add方法天然就会抛出异常`throw new UnsupportedOperationException();`，平时我们使用的都是ArrayList的add方法，它是进行了重写；

### ArrayList和LinkedList的区别

- 实现上，ArrayList是动态数组的实现，LinkedList是双向链表的实现
- 随机访问效率上，ArrayList比LinkedList效率高，非首尾的增加和删除效率上LinkedList比ArrayList效率高
- 内存空间占用上，LinkedList比ArrayList更占内存

### ArrayList和Vector的区别

- Vector是线程安全的，ArrayList是线程不安全的
- ArrayList在性能方面要优于Vector
- ArrayList每次扩容时容量增加50%，Vector每次增加1倍

### 为什么ArrayList的elementData要加上transient修饰

transient是说不希望elementData数组被序列化，ArrayList中重写了writeObject实现：每次序列化时，先调用defaultWriteObject()方法序列化ArrayList中的非transient元素，然后遍历elementData，只序列化已存入的元素，这样既加快了序列化的速度，又减小了序列化之后文件的大小。

### HashSet的实现原理

HashSet 是基于 HashMap 实现的，HashSet的值存放于HashMap的key上，HashMap的value统一为present。

### HashSet如何检查重复

- 添加元素时，判断元素是否存在的依据不仅要比较hash值，还要结合equals方法
- HashSet中的add（）方法会使用HashMap的put方法
- HashMap 的 key 是唯一的，由源码可以看出 HashSet 添加进去的值就是作为HashMap 的key，并且在HashMap中如果K/V相同时，会用新的V覆盖掉旧的V，然后返回旧的V。所以不会重复

### hashmap1.7和1.8的区别

不同点：

- JDK1.7用的是头插法，JDK1.8及之后使用的都是尾插法，因为JDK1.7是用单链表进行的纵向延伸，当采用头插法时会容易出现逆序且环形链表死循环问题。在JDK1.8之后是因为加入了红黑树使用尾插法，能够避免出现逆序且链表死循环的问题。

- 扩容后数据存储位置的计算方式也不一样： 

  在JDK1.7的时候是直接用hash值和需要扩容的二进制数进行&，而在JDK1.8的时候直接用了JDK1.7的时候计算的规律，也就是扩容前的原始位置+扩容的大小值，这种方式就相当于只需要判断Hash值的新增参与运算的位是0还是1即可。

- JDK1.7使用数组+单链表的数据结构，JDK1.8及之后时使用数组+链表+红黑树的数据结构

### 为什么扩容的时候一定必须是2的多少次幂

如果只有2的n次幂的情况时最后一位二进制数才一定是1，这样能最大程度减少hash碰撞

### 为什么JDK1.7的时候是先进行扩容后进行插入，而JDK1.8的时候是先插入后扩容

在JDK1.7中是先进行扩容后进行插入的，当你发现你插入的桶为空时，说明存在值发生了hash冲突，那么就必须扩容。但是如果不发生hash冲突的话，说明当前桶是空的（后面并没有挂有链表），那就等到下一次发生Hash冲突的时候再进行扩容，但是如果以后都没有发生hash冲突，那么就不会进行扩容了，减少了一次无用扩容。

### 为什么在JDK1.8中进行hashmap优化时，把链表转化为红黑树的阈值是8，而不是7或20呢？

如果选择6和8，中间有个差值7，可以有效防止链表和树频繁转换。

由于treenodes的大小大约是常规节点的两倍，因此我们仅在容器包含足够的节点以保证使用时才使用它们，当它们变得太小（由于移除或调整大小）时，它们会被转换回普通的node节点，容器中节点分布在hash桶中的频率遵循泊松分布，桶的长度超过8的概率非常非常小。所以作者应该是根据概率统计而选择了8作为阀值

### 哈希表如何解决Hash冲突

![](https://img-blog.csdn.net/20180905105313470?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

### 为什么hashmap具备下述特点：键-值(key-value)都允许为空，线程不安全，不保证有序，存储位置随时间变化

![](https://img-blog.csdn.net/20180905105402336?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

### 为什么HashMap中String,Integer这样的包装类适合作为key键

![](https://img-blog.csdn.net/20180905105453712?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

### HashMap中的key若Object类型，则需实现哪些方法?

![](https://img-blog.csdn.net/20180905105527545?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

### Hashmap1.7和1.8扩容机制对比

![](https://img-blog.csdn.net/20180905105129591?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

https://blog.csdn.net/qq_36520235/article/details/82417949

### hashmap put方法流程

**JDK1.7：**

- 判断当前数组是否需要初始化。
- 如果 key 为空，则 put 一个空值进去。
- 根据 key 计算出 hashcode。
- 根据计算出的 hashcode 定位出所在桶。
- 如果桶是一个链表则需要遍历判断里面的 hashcode、key 是否和传入 key 相等，如果相等则进行覆盖，并返回原来的值。
- 如果桶是空的，说明当前位置没有数据存入；新增一个 Entry 对象写入当前位置。

**JDK1.8：**

1. 判断当前桶是否为空，空的就需要初始化（resize 中会判断是否进行初始化）。
2. 根据当前 key 的 hashcode 定位到具体的桶中并判断是否为空，为空表明没有 Hash 冲突就直接在当前位置创建一个新桶即可。
3. 如果当前桶有值（ Hash 冲突），那么就要比较当前桶中的 `key、key 的 hashcode` 与写入的 key 是否相等，相等就赋值给 `e`,在第 8 步的时候会统一进行赋值及返回。
4. 如果当前桶为红黑树，那就要按照红黑树的方式写入数据。
5. 如果是个链表，就需要将当前的 key、value 封装成一个新节点写入到当前桶的后面（形成链表）。
6. 接着判断当前链表的大小是否大于预设的阈值，大于时就要转换为红黑树。
7. 如果在遍历过程中找到 key 相同时直接退出遍历。
8. 如果 `e != null` 就相当于存在相同的 key,那就需要将值覆盖。
9. 最后判断是否需要进行扩容。

https://crossoverjie.top/2018/07/23/java-senior/ConcurrentHashMap/

### 为什么头插法会产生死循环

https://blog.csdn.net/littlehaes/article/details/105241194

### HashMap与HashTable的区别

- HashMap是非线程安全的，HashTable是线程安全的，HashMap比HashTable效率高一些
- HashMap中可以用null作为键，HashTable中put进的键值只要有一个null，直接抛NullPointerException
- 创建时如果不指定容量初始值，Hashtable默认的初始大小为11，之后每次扩充为原来的2n+1.HashMap默认的初始化大小为16，之后每次扩充，容量变为原来的2倍。创建时如果给定了容量初始值，那么Hashtable会直接使用你给定的大小，而HashMap会将其扩充为2的幂次方的大小。

### TreeMap

是一个有序的线程不同步的key-value集合，基于红黑树实现，该映射根据**其键的自然顺序进行排序**，或者根据**创建映射时提供的 Comparator 进行排序**（具体取决于使用的构造方法。）

### 如何决定使用 HashMap 还是 TreeMap？

对于在Map中插入、删除和定位元素这类操作，HashMap是最好的选择。然而，假如你需要对一个有序的key集合进行遍历，TreeMap是更好的选择。

### HashMap 和 ConcurrentHashMap 的区别

1. ConcurrentHashMap对整个桶数组进行了分割分段(Segment)，然后在每一个分段上都用lock锁进行保护，相对于HashTable的synchronized锁的粒度更精细了一些，并发性能更好，而HashMap没有锁机制，不是线程安全的。（JDK1.8之后ConcurrentHashMap启用了一种全新的方式实现,利用CAS算法。）
2. HashMap的键值对允许有null，但是ConCurrentHashMap都不允许。

### ConcurrentHashMap 基本结构

首先将数据分为一段一段的存储，然后给每一段数据配一把锁，当一个线程占用锁访问其中一个段数据时，其他段的数据也能被其他线程访问。

**JDK1.7**：

ConcurrentHashMap采用Segment + HashEntry的方式进行实现，结构如下：

一个 ConcurrentHashMap 里包含一个 Segment 数组。Segment 的结构和HashMap类似，是一种数组和链表结构，一个 Segment 包含一个 HashEntry 数组，每个 HashEntry 是一个链表结构的元素，每个 Segment 守护着一个HashEntry数组里的元素，当对 HashEntry 数组的数据进行修改时，必须首先获得对应的 Segment的锁。

![](https://user-gold-cdn.xitu.io/2020/4/13/171735524c5089b8?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

1.该类包含两个静态内部类 HashEntry 和 Segment ；前者用来封装映射表的键值对，后者用来充当锁的角色；

2.Segment 是一种可重入的锁 ReentrantLock，每个 Segment 守护一个HashEntry 数组里得元素，当对 HashEntry 数组的数据进行修改时，必须首先获得对应的 Segment 锁。

**JDK1.8**:

**放弃了Segment臃肿的设计，取而代之的是采用Node + CAS + Synchronized来保证并发安全进行实现**，synchronized只锁定当前链表或红黑二叉树的首节点，这样只要hash不冲突，就不会产生并发，效率又提升N倍。

![](https://user-gold-cdn.xitu.io/2020/4/13/17173552564c22be?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

### ConcurrentHashMap put方法流程

**JDK1.8：**

- 根据 key 计算出 hashcode 。
- 判断是否需要进行初始化。
- `f` 即为当前 key 定位出的 Node，如果为空表示当前位置可以写入数据，利用 CAS 尝试写入，失败则自旋保证成功。
- 如果当前位置的 `hashcode == MOVED == -1`,则需要进行扩容。
- 如果都不满足，则利用 synchronized 锁写入数据。
- 如果数量大于 `TREEIFY_THRESHOLD` 则要转换为红黑树。

### ConcurrentHashMap 扩容流程（还没写）

https://www.jianshu.com/p/487d00afe6ca

1.线程执行put操作，发现容量已经达到扩容阈值，需要进行扩容操作，此时transferindex=tab.length=32

2.扩容线程A 以cas的方式修改transferindex=31-16=16 ,然后按照降序迁移table[31]--table[16]这个区间的hash桶

3.迁移hash桶时，会将桶内的链表或者红黑树，按照一定算法，拆分成2份，将其插入nextTable[i]和nextTable[i+n]（n是table数组的长度）。 迁移完毕的hash桶,会被设置成ForwardingNode节点，以此告知访问此桶的其他线程，此节点已经迁移完毕。

4.此时线程2访问到了ForwardingNode节点，如果线程2执行的put或remove等写操作，那么就会先帮其扩容。如果线程2执行的是get等读方法，则会调用ForwardingNode的find方法，去nextTable里面查找相关元素。

### ConcurrentHashMap为什么不能存值为null的value（主要学习作者的学习方式）

https://mp.weixin.qq.com/s?__biz=MzIxNTQ4MzE1NA==&mid=2247484354&idx=1&sn=80c92881b47a586eba9c633eb78d36f6&chksm=9796d5bfa0e15ca9713ff9dc6e100593e0ef06ed7ea2f60cb984e492c4ed438d2405fbb2c4ff&scene=21#wechat_redirect

## 阻塞队列(BlockingQueue）

实现原理：https://blog.csdn.net/chenchaofuck1/article/details/51660119

阻塞队列与我们平常接触的普通队列(LinkedList或ArrayList等)的最大不同点，在于阻塞队列支出阻塞添加和阻塞删除方法。

- 阻塞添加
  所谓的阻塞添加是指当阻塞队列元素已满时，队列会阻塞加入元素的线程，直队列元素不满时才重新唤醒线程执行元素加入操作。
- 阻塞删除
  阻塞删除是指在队列元素为空时，删除队列元素的线程将被阻塞，直到队列不为空再执行删除操作(一般都会返回被删除的元素)

实现类：

- **ArrayBlockingQueue**：ArrayBlockingQueue 是一个有界的阻塞队列，其内部实现是将对象放到一个数组里。
- **DelayQueue**：DelayQueue 对元素进行持有直到一个特定的延迟到期。注入其中的元素必须实现 java.util.concurrent.Delayed 接口。
- **LinkedBlockingQueue**：LinkedBlockingQueue 内部以一个链式结构(链接节点)对其元素进行存储。如果需要的话，这一链式结构可以选择一个上限。如果没有定义上限，将使用 Integer.MAX_VALUE 作为上限。
- **PriorityBlockingQueue**：PriorityBlockingQueue 是一个无界的并发队列。它使用了和类 java.util.PriorityQueue 一样的排序规则。你无法向这个队列中插入 null 值。所有插入到 PriorityBlockingQueue 的元素必须实现 java.lang.Comparable 接口。因此该队列中元素的排序就取决于你自己的 Comparable 实现。
- **SynchronousQueue**：SynchronousQueue 是一个特殊的队列，它的内部同时只能够容纳单个元素。如果该队列已有一元素的话，试图向队列中插入一个新元素的线程将会阻塞，直到另一个线程将该元素从队列中抽走。同样，如果该队列为空，试图向队列中抽取一个元素的线程将会阻塞，直到另一个线程向队列中插入了一条新的元素。据此，把这个类称作一个队列显然是夸大其词了。它更多像是一个汇合点。

### LinkedBlockingQueue和ArrayBlockingQueue（没写完）

ArrayBlockingQueue内部的阻塞队列是通过重入锁ReenterLock和Condition条件队列实现的，所以ArrayBlockingQueue中的元素存在公平访问与非公平访问的区别，对于公平访问队列，被阻塞的线程可以按照阻塞的先后顺序访问队列，即先阻塞的线程先访问队列。而非公平队列，当队列可用时，阻塞的线程将进入争夺访问资源的竞争中，也就是说谁先抢到谁就执行，没有固定的先后顺序。

https://blog.csdn.net/javazejian/article/details/77410889

## 生产者消费者模式的实现（还没写）



## 创建线程的三种方式

- 采用实现Runnable创建多线程
- 使用继承Thread类的方式创建多线程
- 采用实现Callable接口的方式创建多线程
- 通过创建线程池来创建线程

## 线程状态转换关系

![](https://user-gold-cdn.xitu.io/2018/4/30/163159b8a740b329?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

## sleep()和wait()的区别

![](https://yueqilai-images.oss-cn-beijing.aliyuncs.com/20180723171041981.png)

## volatile(还没写)

## 多线程8锁

### 公平锁/非公平锁

1. 公平锁是指多个线程按照申请锁的顺序来获取锁。（先到先得，非常公平）
2. 非公平锁是指多个线程获取锁的顺序并不是按照申请锁的顺序，有可能后申请的线程比先申请的线程优先获取锁。有可能，会造成优先级反转或者饥饿现象。

### 可重入锁

可重入锁又名递归锁，是指在同一个线程在外层方法获取锁的时候，在进入内层方法会自动获取锁。

### 独享锁/共享锁

1. 独享锁是指该锁一次只能被一个线程所持有。
2. 共享锁是指该锁可被多个线程所持有。

### 互斥锁/读写锁

上面讲的独享锁/共享锁就是一种广义的说法，互斥锁/读写锁就是具体的实现。
互斥锁在Java中的具体实现就是ReentrantLock
读写锁在Java中的具体实现就是ReadWriteLock

### 乐观锁/悲观锁

乐观锁与悲观锁不是指具体的什么类型的锁，而是指看待并发同步的角度。

1. 悲观锁认为对于同一个数据的并发操作，一定是会发生修改的，哪怕没有修改，也会认为修改。因此对于同一个数据的并发操作，悲观锁采取加锁的形式。悲观的认为，不加锁的并发操作一定会出问题。
2. 乐观锁则认为对于同一个数据的并发操作，是不会发生修改的。在更新数据的时候，会采用尝试更新，不断重新的方式更新数据。乐观的认为，不加锁的并发操作是没有事情的。

实现：

1. 悲观锁在Java中的使用，就是利用各种锁。
2. 乐观锁在Java中的使用，是无锁编程，常常采用的是CAS算法，典型的例子就是原子类，通过CAS自旋实现原子操作的更新。

### 分段锁

​	分段锁其实是一种锁的设计，并不是具体的一种锁，对于ConcurrentHashMap而言，其并发的实现就是通过分段锁的形式来实现高效的并发操作。ConcurrentHashMap内部就是用了分段锁。
​    分段锁的设计目的是细化锁的粒度，当操作不需要更新整个数组的时候，就仅仅针对数组中的一项进行加锁操作。

### 偏向锁/轻量级锁/重量级锁

1. 偏向锁是指一段同步代码一直被一个线程所访问，那么该线程会自动获取锁。降低获取锁的代价。
2. 轻量级锁是指当锁是偏向锁的时候，被另一个线程所访问，偏向锁就会升级为轻量级锁，其他线程会通过自旋的形式尝试获取锁，不会阻塞，提高性能。
3. 重量级锁是指当锁为轻量级锁的时候，另一个线程虽然是自旋，但自旋不会一直持续下去，当自旋一定次数的时候，还没有获取到锁，就会进入阻塞，该锁膨胀为重量级锁。重量级锁会让其他申请的线程进入阻塞，性能降低。

**从偏向锁->轻量级锁->重量级锁 是锁升级过程，该过程不可逆**

### 自旋锁

在Java中，自旋锁是指尝试获取锁的线程不会立即阻塞，而是采用循环的方式去尝试获取锁，这样的好处是减少线程上下文切换的消耗，缺点是循环会消耗CPU。

## 锁机制（b站那个视频没总结完）

在Java中每个对象都有一把锁，存放于对象头中，锁中记录当前对象是被哪个线程所占用。

对象的结构又分为对象头，实例数据和对齐填充，对齐填充是为了满足Java对象的大小必须是8字节的倍数而设计。实例数据是在初始化时设定的属性和状态的内容。

对象头存放对象本身的运行时信息，包含两部分Mark word和class pointer。class pointer就是一个指针，指向当前对象类型所在方法区中的类型数据。mark word存储了很多和当前对象运行时状态有关的数据。(那个表格)mark word最后两位为锁标志位。
synchronized编译后生成monitorenter和monitorexit两个字节码指令来进行线程同步。monitor的原理是首先entryset中聚集了一些想要进入monitor的线程，他们正处于waiting状态，假设线程a成功进入monitor，它就变为active状态，此时若线程执行途中遇到了一个判断条件需要暂时让出执行权，它将进入wait set，状态变为waiting，此时entry set中的线程可以进入monitor。当monitor中的线程执行完毕后可以唤醒其他线程继续执行。synchronized可能会有性能问题，因为monitor是依赖操作系统的mutex lock来实现的。JAVA线程实际是对操作系统线程的映射，所以每当挂起或唤醒一个线程都要切换操作系统内核态。
1.6开始，对synchronized进行了优化，锁总共有四种状态。(后面有点长)

## 为什么synchronized无法禁止指令重排，却能保证有序性？

synchronized通过排他锁的方式就保证了同一时间内，被synchronized修饰的代码是单线程执行的。

## 线程池

### 参数

```java
ThreadPoolExecutor(int corePoolSize,
                              int maximumPoolSize,
                              long keepAliveTime,
                              TimeUnit unit,
                              BlockingQueue<Runnable> workQueue,
                              ThreadFactory threadFactory,
                              RejectedExecutionHandler handler) 
```

- corePoolSize：核心线程数量

  如果线程池收到任务，且线程池内部线程数量没有达到corePoolSize，线程池会直接给此任务创建一个新线程来处理此任务。具体是创建一个Work对象，此Work持有此任务Runnable、此线程Thread的引用。最后将此Work放入一个名叫workers的Set集合中。0 =< workers.size <=maximumPoolSize。

- maximumPoolSize: 最大允许线程数量

  线程池内部线程数量已经达到核心线程数量，即corePoolSize，并且任务队列已满，此时如果继续有任务被提交，将判断线程池内部线程总数是否达到maximumPoolSize，如果小于maximumPoolSize，将继续使用线程工厂创建新线程。如果线程池内线程数量等于maximumPoolSize，就不会继续创建线程，将触发拒绝策略RejectedExecutionHandler。新创建的同样是一个Work对象，并最终放入workers集合中。

- keepAliveTime, unit:超出线程的存活时间

  当线程池内部的线程数量大于corePoolSize，则多出来的线程会在keepAliveTime时间之后销毁。

- workQueue:任务队列

  线程池需要执行的任务的队列，通常有固定数量的ArrayBlockingQueue,无限制的LinkedBlockingQueue.

- threadFactory:线程工厂，用于创建线程

- handler：任务拒绝策略

  当任务队列已满，又有新的任务进来时，会回调此接口。

### 四种拒绝策略

`ThreadPoolExecutor.AbortPolicy`:丢弃任务并抛出RejectedExecutionException异常。
`ThreadPoolExecutor.DiscardPolicy`：丢弃任务，但是不抛出异常。
`ThreadPoolExecutor.DiscardOldestPolicy`：丢弃队列最前面的任务，然后重新提交被拒绝的任务
`ThreadPoolExecutor.CallerRunsPolicy`：由调用线程（提交任务的线程）处理该任务

### 工作流程

![](https://upload-images.jianshu.io/upload_images/4134622-fbbdbcb6bcc00178.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)

### 如何实现线程复用

1、当Thread的run方法执行完一个任务之后，会循环地从阻塞队列中取任务来执行，这样执行完一个任务之后就不会立即销毁了；

2、当工作线程数小于核心线程数，那些空闲的核心线程再去队列取任务的时候，如果队列中的Runnable数量为0，就会阻塞当前线程，这样线程就不会回收了

https://www.jianshu.com/p/5e952ab2c41b

## CountDownLatch,CyclicBarrier,Semaphore(没写完)

CountDownLatch:

​	允许一个或多个线程一直等待，直到一组在其他线程执行的操作全部完成

​	当一个线程调用await方法时，就会阻塞当前线程。每当有线程调用一次countDown方法时，计数就会减1。当count的值等于0的时候，被阻塞的线程才会继续运行。

CyclicBarrier:

## AQS（没写完）

AQS 全称是 AbstractQueuedSynchronizer，是一个用来构建**锁**和**同步器**的框架，它维护了一个共享资源 state 和一个 FIFO 的等待队列，底层利用了 CAS 机制来保证操作的原子性。

**AQS锁的实现原理：**

![img](https://mmbiz.qpic.cn/mmbiz_jpg/OyweysCSeLUw3oEcJTUMphCBvlHmY65EaNibqm2VepgYQCicnCf3ibjdLUNjxNg3Z7YmWPMYC16ZqmwvT72DQ0FqA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



以实现独占锁为例（即当前资源只能被一个线程占有），其实现原理如下：state 初始化 0，在多线程条件下，线程要执行临界区的代码，必须首先获取 state，某个线程获取成功之后， state 加 1，其他线程再获取的话由于共享资源已被占用，所以会到 FIFO 等待队列去等待，等占有 state 的线程执行完临界区的代码释放资源( state 减 1)后，会唤醒 FIFO 中的下一个等待线程（head 中的下一个结点）去获取 state。

state 由于是多线程共享变量，所以必须定义成 volatile，以保证 state 的可见性, 同时虽然 volatile 能保证可见性，但不能保证原子性，所以 AQS 提供了对 state 的原子操作方法，保证了线程安全。

另外 AQS 中实现的 FIFO 队列（CLH 队列）其实是双向链表实现的，由 head, tail 节点表示，head 结点代表当前占用的线程，其他节点由于暂时获取不到锁所以依次排队等待锁释放。

### 获取锁

## JDBC流程

第一步：加载Driver类，注册数据库驱动；
第二步：通过DriverManager,使用url，用户名和密码建立连接(Connection)；
第三步：通过Connection，使用sql语句打开Statement对象；
第四步：执行语句，将结果返回resultSet；
第五步：对结果resultSet进行处理；
第六步：倒叙释放资源resultSet-》preparedStatement-》connection。

# JVM

## 四种引用

### 虚引用

主要用来**跟踪对象**被垃圾回收器**回收**的活动。 

**虚引用**与**软引用**和**弱引用**的一个区别在于：虚引用必须和引用队列(ReferenceQueue)联合使用。当垃圾回收器准备回收一个对象时，如果发现它还有虚引用，就会在回收对象的内存之前，把这个虚引用加入到与之关联的引用队列中。

简单的说是，虚引用是用来判断对象是否被即将回收，然后程序再采取相应的措施

```java
    String str = new String("abc");
    ReferenceQueue queue = new ReferenceQueue();
    // 创建虚引用，要求必须与一个引用队列关联
    PhantomReference pr = new PhantomReference(str, queue);
复制代码
```

## TLAB分配

每个线程在Java堆中预先分配一小块内存，然后再给对象分配内存的时候，直接在自己这块”私有”内存中分配，当这部分区域用完之后，再分配新的”私有”内存。

**“堆是线程共享的内存区域”这句话并不完全正确，因为TLAB是堆内存的一部分，他在读取上确实是线程共享的，但是在内存分分配上，是线程独享的。**

## 为什么用元空间

1、字符串存在永久代中，容易出现性能问题和内存溢出。

2、类及方法的信息等比较难确定其大小，因此对于永久代的大小指定比较困难，太小容易出现永久代溢出，太大则容易导致老年代溢出。

3、永久代会为 GC 带来不必要的复杂度，并且回收效率偏低。

## 类加载过程

![](https://user-gold-cdn.xitu.io/2020/2/22/1706abac42fee7f4?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

**1.加载(Loading):**

做的事情：

1. 通过一个类的全限定名获取定义此类的二进制字节流
2. 将这个字节流所代表的的静态存储结构转化为方法区的运行时数据结构
3. **在内存中生成一个代表这个类的 `java.lang.Class` 对象**，作为方法区这个类的各种数据的访问入口

加载`.class`文件的方式：

- 从本地系统中直接加载

- 通过网络获取，典型场景：Web Applet

- 从zip压缩文件中读取，成为日后jar、war格式的基础

- 运行时计算生成，使用最多的是：动态代理技术

- 由其他文件生成，比如 JSP 应用

- 从专有数据库提取.class 文件，比较少见

- 从加密文件中获取，典型的防 Class 文件被反编译的保护措施

**2. 连接（Linking）**

- **验证（Verify）**

  目的在于确保Class文件的字节流中包含信息符合当前虚拟机要求，保证被加载类的正确性，不会危害虚拟机自身安全，主要包括四种验证：**文件格式验证，元数据验证，字节码验证，符号引用验证**

- **准备（Prepare）**

  为类变量分配内存并且设置该类变量的默认初始值，即**零值**

  注意：

  - 这里不包含用final修饰的static，因为final在编译的时候就会分配了，准备阶段会显示初始化
  - 这里**不会为实例变量分配初始化**，类变量会分配在**方法区**中，而实例变量是会随着对象一起分配到Java堆中

- **解析（Resolve）**

  将常量池内的符号引用转换为直接引用的过程，符号引用就是一组符号来描述所引用的目标。直接引用就是直接指向目标的指针，相对偏移量或一个间接定位到目标的句柄。解析动作主要针对类或接口、字段、类方法、接口方法、方法类型等。

  

**3.初始化(Initialization)**

初始化阶段就是执行**类构造器方法**<clinit>()的过程，此方法不需要定义，是javac编译器自动收集类中的所有类变量的赋值动作和静态代码块中的语句合并而来，构造器方法中指令按语句在源文件中出现的顺序执行。若该类具有父类，JVM会保证子类的`<clinit>()`执行前，父类的`<clinit>()`已经执行完毕，虚拟机必须保证一个类的`<clinit>()`方法在多线程下被同步加锁。

## 对象从年轻代进入老年代的时机

- Young GC时，To Survivor区不足以存放存活的对象，对象会直接进入到老年代。
- 经过多次Young GC后，如果存活对象的年龄达到了设定阈值(默认是15)，则会晋升到老年代中。
- 动态年龄判定规则，To Survivor区中相同年龄的对象，如果其大小之和占到了 To Survivor区一半以上的空间，那么大于此年龄的对象会直接进入老年代，而不需要达到默认的分代年龄。
- 大对象：由-XX:PretenureSizeThreshold启动参数控制，若对象大小大于此值，就会绕过新生代, 直接在老年代中分配。

## 触发Full GC的时机

- 晋升到老年代的对象大于了老年代的剩余空间
- 老年代的内存使用率达到了一定阈值（可通过参数调整）
- 空间分配担保：在Young GC之前，会先检查老年代最大可用的连续空间是否大于新生代所有对象的总空间。如果小于，说明Young GC是不安全的，则会查看参数 HandlePromotionFailure 是否被设置成了允许担保失败，如果不允许则直接触发Full GC；如果允许，那么会进一步检查老年代最大可用的连续空间是否大于历次晋升到老年代对象的平均大小，如果小于也会触发 Full GC。
- Metaspace（元空间）在空间不足时会进行扩容，当扩容到了`-XX:MetaspaceSize` 参数的指定值时，也会触发Full GC。
- `System.gc()` 或者`Runtime.gc()` 被显式调用时，触发Full GC。

## Minor GC的触发条件

当 Eden 区的空间耗尽，这个时候 Java虚拟机便会触发一次 **Minor GC**来收集新生代的垃圾，存活下来的对象，则会被送到 Survivor区。

## “无用的类”的判断条件

- 该类所有的实例都已经被回收
- 加载该类的ClassLoader已经被回收
- 该类对应的`java.lang.Class`对象没有在任何地方被引用，无法在任何地方通过反射访问该类的方法

## 如何判断一个常量是废弃常量

没有任何String对象引用该字符串常量

## 双亲委派机制

**过程**：

源ClassLoader先判断该Class是否已加载，如果已加载，则返回Class对象；如果没有则委托给父类加载器。
父类加载器判断是否加载过该Class，如果已加载，则返回Class对象；如果没有则委托给祖父类加载器。
依此类推，直到始祖类加载器（引用类加载器）。
始祖类加载器判断是否加载过该Class，如果已加载，则返回Class对象；如果没有则尝试从其对应的类路径下寻找class字节码文件并载入。如果载入成功，则返回Class对象；如果载入失败，则委托给始祖类加载器的子类加载器。
始祖类加载器的子类加载器尝试从其对应的类路径下寻找class字节码文件并载入。如果载入成功，则返回Class对象；如果载入失败，则委托给始祖类加载器的孙类加载器。
依此类推，直到源ClassLoader。
源ClassLoader尝试从其对应的类路径下寻找class字节码文件并载入。如果载入成功，则返回Class对象；如果载入失败，源ClassLoader不会再委托其子类加载器，而是抛出异常。

**双亲委派模型能保证基础类仅加载一次，不会让jvm中存在重名的类。**

**自己实现ClassLoader时只需要继承ClassLoader类，然后覆盖findClass（String name）方法即可完成一个带有双亲委派模型的类加载器。**

**破坏双亲委派模型：**

1.代码热替换，在不重启服务器的情况下可以修改类的代码并使之生效。

热部署步骤：

1. 销毁自定义classloader(被该加载器加载的class也会自动卸载)；
2. 更新class
3. 使用新的ClassLoader去加载class

2.JDBC

我们知道Java核心API（比如rt.jar包）是使用Bootstrap ClassLoader类加载器加载的，而用户提供的Jar包是由AppClassLoader加载的。如果一个类由类加载器加载，那么这个类依赖的类也是由相同的类加载器加载的。

- 第一，从META-INF/services/java.sql.Driver文件中获取具体的实现类名“com.mysql.jdbc.Driver”
- 第二，加载这个类，这里肯定只能用class.forName("com.mysql.jdbc.Driver")来加载

好了，问题来了，Class.forName()加载用的是调用者的Classloader，这个调用者DriverManager是在rt.jar中的，ClassLoader是启动类加载器，而com.mysql.jdbc.Driver肯定不在/lib下，所以肯定是无法加载mysql中的这个类的。这就是双亲委派模型的局限性了，父级加载器无法加载子级类加载器路径中的类。

那么，这个问题如何解决呢？按照目前情况来分析，这个mysql的drvier只有应用类加载器能加载，那么我们只要在启动类加载器中有方法获取应用程序类加载器，然后通过它去加载就可以了。这就是所谓的线程上下文加载器。

**线程上下文类加载器让父级类加载器能通过调用子级类加载器来加载类，这打破了双亲委派模型的原则**

简单的说就是破坏了可见性

3.tomcat中的每个项目之间能加载不用的lib

## 全盘负责

“全盘负责”是指当一个ClassLoader装载一个类时，除非显示地使用另一个ClassLoader，则该类所依赖及引用的类也由这个ClassLoader载入。

## 并发标记

https://segmentfault.com/a/1190000021820577

在遍历对象图的过程中，把访问都的对象**按照"是否访问过"这个条件**标记成以下三种颜色：

**白色：表示对象尚未被垃圾回收器访问过**。显然，在可达性分析刚刚开始的阶段，所有的对象都是白色的，若在分析结束的阶段，仍然是白色的对象，即代表不可达。

**黑色：表示对象已经被垃圾回收器访问过，且这个对象的所有引用都已经扫描过**。黑色的对象代表已经扫描过，它是安全存活的，如果有其它的对象引用指向了黑色对象，无须重新扫描一遍。黑色对象不可能直接（不经过灰色对象）指向某个白色对象。

**灰色：表示对象已经被垃圾回收器访问过，但这个对象至少存在一个引用还没有被扫描过**。

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/1460000021820594)

怎么解决"对象消失"问题呢？

条件一：赋值器插入了一条或者多条从黑色对象到白色对象的新引用。

条件二：赋值器删除了全部从灰色对象到该白色对象的直接或间接引用。

你在结合我们上面出现过的图捋一捋上面的这两个条件，是不是当且仅当的关系：

黑色对象5到白色对象9之间的引用是新建的，对应条件一。

黑色对象6到白色对象9之间的引用被删除了，对应条件二。

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/1460000021820598)

**CMS是基于增量更新来做并发标记的，G1则采用的是原始快照的方式。**

增量更新

黑色对象一旦插入了指向白色对象的引用之后，它就变回了灰色对象。

原始快照

无论引用关系删除与否，都会按照刚刚开始扫描那一刻的对象图快照开进行搜索。

## G1收集器原理

https://segmentfault.com/a/1190000021878102

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/1460000021878115)

h表示大对象

G1的堆内存被划分为多个大小相等的 Region ，但是 Region 的总个数在 2048 个左右，默认是 2048 。对于一个 Region 来说，是逻辑连续的一段空间，其大小的取值范围是 1MB 到 32MB 之间。

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/1460000021878130)

![img](https://gitee.com/xurunxuan/picgo/raw/master/img/1460000021878134)

## 常量池

https://mp.weixin.qq.com/s/Av2phrOe_TXnRwD0SeYPCg

![image-20201107112058414](https://gitee.com/xurunxuan/picgo/raw/master/img/image-20201107112058414.png)

class常量池

- 类和接口的全限定名
- 字段的名称和描述符
- 方法的名称和描述符

**运行时常量池就是用来存放 class 常量池中的内容的**

1. 字符串常量池本质就是一个哈希表
2. 字符串常量池中存储的是字符串实例的引用
3. 字符串常量池在被整个 JVM 共享
4. 在解析运行时常量池中的符号引用时，会去查询字符串常量池，确保运行时常量池中解析后的直接引用跟字符串常量池中的引用是一致的

## 保守和非保守GC

https://zuozuo.gitbooks.io/reading-notes-of-garbage-collection/content/chapter6_bao_shou_shi_gc.html

**保守式GC(Conservative GC)指的是: 不能识别指针和非指针的GC**

**准确式GC(Exact GC)能够正确识别出指针和非指针** 	

相信大家看下来已经知道准确意味 JVM 需要清晰的知晓对象的类型，包括在栈上的引用也能得知类型等。

能想到的可以在指针上打标记，来表明类型，或者在外部记录类型信息形成一张映射表。

HotSpot 用的就是映射表，这个表叫 OopMap。

在 HotSpot 中，对象的类型信息里会记录自己的 OopMap，记录了在该类型的对象内什么偏移量上是什么类型的数据，而在解释器中执行的方法可以通过解释器里的功能自动生成出 OopMap 出来给 GC 用。

被 JIT 编译过的方法，也会在特定的位置生成 OopMap，记录了执行到该方法的某条指令时栈上和寄存器里哪些位置是引用。

这些特定的位置主要在：

1. 循环的末尾（非 counted 循环）
2. 方法临返回前 / 调用方法的call指令后
3. 可能抛异常的位置

这些位置就叫作安全点(safepoint)。

那为什么要选择这些位置插入呢？因为如果对每条指令都记录一个 OopMap 的话空间开销就过大了，因此就选择这些个关键位置来记录即可。

所以在 HotSpot 中 GC 不是在任何位置都能进入的，只能在安全点进入。

至此我们知晓了可以在类加载时计算得到对象类型中的 OopMap，解释器生成的 OopMap 和 JIT 生成的 OopMap ，所以 GC 的时候已经有充足的条件来准确判断对象类型。

因此称为准确式 GC。

https://mp.weixin.qq.com/s/AZ_Xv28cF1xxloluJaniww

# 算法题

## 只出现一次的数字(136)

因为剩下的数字只出现两次，一异或就没了

```java
// a^a=0 0^a=a
class Solution {
    public int singleNumber(int[] nums) {
        if(nums.length == 0)
            return 0;
        else {
            int ans = 0;
            for(int i = 0; i < nums.length; i ++) {
                ans ^= nums[i];
            }
            return ans;
        }
    }
}
```



