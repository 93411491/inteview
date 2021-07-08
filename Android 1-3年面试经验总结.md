# Android 1-3年面试经验总结

## Java基础

- 强引用，弱引用，软引用，虚引用之前的区别
- Mvp，Mvc与Mvvm的区别
- mvp的缺点以及有点
- mvvm的缺点以及有点
- 各个基本数据类型所占的字节大小
- 各排序算法的时间复杂度
- 如何理解快速排序的时间复杂度为nlogn
  - 公式推导
  - 快速排序可以视为一个二叉树，每一次遍历确定一个节点，时间复杂度为logn，遍历n遍，因此为nlogn

- jvm相关
  - 运行时内存区域划分（各分区的是否线程共享，起到的作用以及其中存储的数据）
    - 方法区
    - 虚拟机栈
    - 本地方法栈
    - 程序计数器
    - 堆内存
  - 垃圾回收机制
    - 垃圾判断算法
      - 引用计数法
      - gc root
    - 垃圾回收算法
      - 标记清除
      - 复制
      - 标记整理
      - 分代收集
  - classloader的双亲委托机制以及源码分析
- 什么情况下重写equals时需要重写hashcode，为什么？
- 反射
  - 类加载的原理
  - 类加载的过程
  - 是否可以修改final类型的变量
- 代理模式
  - 代理模式的架构
  - 静态代理
  - 动态代理（原理）
- 注解的原理
- HashMap
  - 底层实现原理（1.8版本）
  - 扩容机制
  - 为什么要用红黑树，以及使用红黑树后查找的时间复杂度是多少（logn）
- ConcurrentHashmap
  - 为什么高并发条件下不推荐使用hashmap
  - 1.7上的实现原理
  - 1.8上的实现原理

- String，StringBuilder，StringBuffer之间的区别
- 单例模式
  - 饿汉式
  - 懒汉式
    - 懒汉式线程安全
  - 双重锁
    - 双重锁中两个if分别祈祷什么作用
    - 为什么要使用volatile，起到了什么作用
  - 静态内部类
  - 枚举
  - 静态内部类与枚举实现单例的原理
- TheadLocal
  - 概念
  - 原理与作用
  - 导致的内存泄露问题原因
- 进程与线程的区别
- 线程池的各参数之间的意思
- 向线程池中添加数据时的流程

- Java中主流的锁
  - 乐观锁与悲观锁的概念
  - 乐观锁的两种实现方式
    - 版本号与CAS原理
  - 锁升级过程
  - 死锁产生的条件，如何避免死锁
- syncronized与volatile的区别
- 使用syncronized修饰静态方法与成员方法有什么区别
- 使用syncronized时，锁信息保存在堆内存的什么位置

## 计算机网络

- Http各版本之间的区别
- get与post之间的区别
- HTTPS与HTTP之间的区别
- TCP建立网络连接的过程
- TCP与UDP的区别
- UDP通常应用在什么场景
- 在浏览器中输入网址后确定，之后的流程是什么
- DNS解析域名的过程
- Https中ssl加密过程
- 网络分层以及每一层的作用
- 什么是中间人攻击，HTTPS可以抵御中间人攻击么

## Android

- Activity的生命周期
- Activtiy的启动模式
- 两个activity进行跳转时所经历的生命周期
- Fragment的生命周期
- Service的生命周期
- 前台service与后台service之间的区别
- 如何使得后台service进行保活
- Activity在framework层的启动流程（也可以理解为ams，pms与wms之间的联系）
  - 当使用startActivity方法启动activtiy时，首先ams首先通过intent中存放的activity信息在packagemamagerservice中查找对应的activity，然后拿到对应activity信息后通过zygote进程fork出一个应用进程，在ams中持有这个应用进程的代理类，通过该代理类进行两个进程间的通信。最后把这个avtivity对应的decorview添加到wms中的ViewRootImp中。
- Activity异常销毁时会执行的方法，其中的数据保存在什么中
- bundle和intent存储数据的大小限制
- Service两种启动模式的区别
- IntentService的原理
- Binder进程间通信原理
- Binder中server进程与client进程是如何进行交互的
- 广播种类
- localBroadcast与全局广播的区别
- localBroadcast的实现原理
- Android中线程池最大线程数定义多少合适
- Handler消息机制解析
- Handler导致的内存泄露
- HandlerThread原理
- IdleHandler原理
- handler中的同步屏障
- Hander.postDelay的原理
- Sharepreference的两种提交方式
- Sharepreference是线程安全的么，是进程安全的么，如何保证进程安全
- Serializable与Parcelable的区别
- Fragment与ViewPager的两个适配器
- ViewPager与Fragment的懒加载与预加载
- Fragment中add与replace的区别
- ConstraintLayout与RelativeLayout的区别
- 什么时候初始化ContentProvider
- View的事件分发体系
  - 解析activity的构成
  - View的事件分发流程
  - View是如何处理事件的
  - onMeasure，onLayout与onDraw的区别
- View的绘制流程
- invalidate的作用
- requestLayout的作用
- invalidate与requestLayout 的区别
- RecycleView与ListView的缓存机制
- RecycleView的局部刷新原理
- View.post与Handler.post的区别
- LeakCanary的分析内存泄露的原理
- LeakCanary中如何打印引用的调用链的
- Bitmap的内存优化
  - 单个像素的字节大小
  - Bitmap计算使用内存的公式
  - 优化方式
- 应用冷启动与热启动的区别

## 开源框架

- Glide图片加载原理
- EventBus原理
- OKHttp的原理，Retrofit原理
- Jetpack组件中ViewModel，LifeCycle与LiveData的原理
- 插件化框架原理
- 组件化的原理，组件化中各模块是如何进行通讯的

