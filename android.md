# Android基础知识

![Android知识图谱](http://o8ydbqznc.bkt.clouddn.com/markdown/androidknowledge.png)

## 基础知识

### Java基础

1. 重载与重写的区别

    **重载**和**重写**是多态性的不同体现；**重写**是子类对父类相同方法(相同方法名、参数与返回类型)的覆写，子类对象使用这个方法是将调用子类中的实现；**重载**是一个类中多个同名方法的不同实现，它们仅方法名相同，参数类型、个数不同，返回值类型也可不同(不可仅返回值类型不同)。

2. String、StringBuffer与StringBuilder的区别

    **String**是字符串常量;
    **StringBuffer**字符串变量(线程安全);
    **StringBuilder**字符串变量(非线程安全).

3. String类能否被继承？

    String类是final类,不可以被继承.

4. switch支持的数据类型有哪些？

    java switch 在 **jdk1.6**以前支持五种数据类型:`byte`、`char`、`short`、`int`、`enum`, **jdk1.7**中为6中:`byte`、`char`、`short`、`int`、`enum`、`String`.

5. final、finally与finalize的区别

    **final**用于什么声明属性、方法和类，分别表示属性不可变、方法不可覆盖、类不可被继承
    **finally**是异常捕获处理语句结构的一部分, 表示无论异常是否发生都会执行的
    **finalize**是Object类的一个方法，在垃圾回收器执行的时候回调用被回收对象的此方法，可以覆盖此方法提供垃圾回收是的其他资源回收，例如关闭文件等。

6. ArrayList, Vector, LinkedList的存储性能和特性

    **ArrayList**和**Vector**都是使用数组来存储数据，此数组元素数大于实际存储的数据一边能够增加和插入元素，他们都允许直接按照序号索引元素，但是插入元素涉及数组元素移动等内存操作，所以索引数据快，但插入删除数据慢; **Vector**由于使用了`synchronized`方法(线程安全)，通常性能上较ArrayList差; **LinkedList**使用双向链表实现存储，按照序号索引数据需要前向或后向遍历，但是插入数据时只需要修改当前项的前后节点即可，所以插入速度快但索引慢.

7. Collection和Collections的区别

    **Collection**是集合类的上级接口，继承于它的接口主要有Set何List;
    **Collections**是针对集合类的一个工具类，它提供了一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作.

8. sleep与wait的区别

    1）sleep来自Thread类，使用时需要捕获异常; wait来自Object类，使用时不需要捕获异常;<br/>
    2）sleep方法没有释放锁，wait方法释放了锁，使得其他线程可以使用同步控制块或者方法;<br/>
    3) sleep不出让系统资源，wait是进入线程等待池等待，出让系统资源，其他线程可以占用CPU;<br/>
    4) sleep(milliseconds)可以用时间指定使它自动唤醒过来，如果时间不到只能调用interrupt()强行打断; 一般wait不会加时间限制，因为如果wait线程的运行资源不够，再出来也没用，要等待其他线程调用notify/notifyAll唤醒等待池中的所有线程，才会进入就绪队列等待OS分配系统资源;<br/>
    5）wait，notify和notifyAll只能在同步控制方法或者同步控制块里面使用，而sleep可以在任何地方使用 .

9. 同步和异步有什么不同，在什么情况下使用

    如果数据需要在线程间共享，则必须进行同步存取。例如正在写的数据以后可能被另一个线程读到，或者正在读的数据可能已经被另一个线程写过了，那么这些数据就是共享数据，需要同步存储才能避免出错;<br/>
    应用程序在进行耗时操作时，为了不阻塞UI以及用户交互响应，需要采用异步编程.

10. 抽象类与接口的区别

    abstract关键字修饰的方法为抽象方法，一个类中只要有一个抽象方法，就必须用abstract定义该类，即抽象类;<br/>
    用interface修饰的类即为接口，里面的方法都是抽象方法，接口里面的字段都是公有字段，即public static final修饰的字段.

11. 接口是否可以继承接口？抽象类是否可以实现接口？抽象类是否可以继承实体类？

    接口可以继承接口;<br/>
    抽象类可以实现(implements)接口;<br/>
    抽象类可以继承实体类，但前提是实体类必须有明确的构造函数.

12. abstract的方法是否可以同时static？是否可以同时native？是否可以同时是synchronized？
13. 线程中wait、join、sleep、yield、notify、notifyall、synchronized的区别与联系
14. 单例模式的写法 
15. HashMap

    HashMap是一个存储键值对(key-value)映射的散列表;


### 数据结构

- 链表

- 二叉树

    中序遍历

- 红黑树

### 常见算法

- 排序

- 查找

- 动态规划

### 面向对象思想

- 封装

- 继承

- 多态

### 开发环境

- Eclipse

- Android Studio

### Android SDK

### Activity

- 声明周期

### Service

- startService

- bindService

- IntentService

    IntentService:异步处理服务，新开一个线程：handlerThread在线程中发消息，然后接受处理完成后，会清理线程，并且关掉服务。IntentService有以下特点：
    1. 它创建了一个独立的工作线程来处理所有的通过onStartCommand()传递给服务的intents。
    2. 创建了一个工作队列，来逐个发送intent给onHandleIntent()。
    3. 不需要主动调用stopSelft()来结束服务。因为，在所有的intent被处理完后，系统会自动关闭服务。
    4. 默认实现的onBind()返回null
    5. 默认实现的onStartCommand()的目的是将intent插入到工作队列中

### BroadcastReceiver

- 静态注册

- 动态注册

### ContentProvider

### Application

### ActionBar

### Fragment

### Desktop Widget

### AndroidManifest
- 四大组件
- 启动模式
- 权限
- 主题theme
- intent-filter

## UI

### Layout
- FrameLayout
- LinearLayout
- TableLayout
- GridLayout
- RelativeLayout
- DrawerLayout
- SlidingPanelLayout
- CoordinatorLayout
- ConstraintLayout

### View

- 事件分发机制
dispatchTouchEvent->onInterceptTouchEvent(false:向子View分发 true:return)->onTouch(true)->return
dispatchTouchEvent->onInterceptTouchEvent(false:向子View分发 true:return)->onTouch(false)->onTouchEvent->Click

### Custom View

### anim

- View Animation
1. Tween Animation
2. Frame Animation

- Proterty Animation
1. ValueAnimator
2. ObjectAnimator
3. AnimatorSet

### Resource

- res
1. anim
2. animator
3. drawable
4. mipmap
5. interpolator
6. layout
7. menu
8. raw
9. values
1) arrays
2) attrs
3) bools
4) colors
5) string
6) styles
10. xml

- assets

AssetManager

### OenGL


## 通信

### Http

### Socket

### Bluetooth

### NFC

### Headset

### USB

### Wifi


## 数据持久化

### Sqlite
- SQLiteOpenHelper
- ContentProvider

### File
- Internal Storage
- External Storage

### SharePreferences

## 性能

### UI优化

### 内存优化
- OOM
- ANR
- 分析
1. Heap
2. adb shell
3. TraceView
4. Dalvik日志
5. logcat
6. MAT

### 电量优化

### 流量优化

## 编译

### JVM、Dalvik与Art的区别

## 调试

### Logcat

### adb

- 命令行控制手机

```
#进入手机交互模式
adb shell
#命令控制输入文本
input text 123456
#命令控制输入按键值 keycode可百度查
input keyevent 7
input keyevent KEYCODE_1
input keyevent KEYCODE_HOME
#点击坐标(123,345)
input tab 123 345
#从坐标(1,2)滑动到(100,300),200毫秒内
input swipe 1 2 100 300 200

#截图
adb shell screencap /sdcard/1.png
#录屏 只能使用**Ctrl+C**停止
adb shell screenrecord /sdcard/1.mp4
#下载手机文件到本地
adb pull /sdcard/1.mp4 .
```

### HierachyViewer

### TraceView

### Heap

### Lint


## 适配

### OS Version

### Screen Size

### Screen px


## 测试

### Monkey

### MonkeyRunner

### JUnit

### Robotium

### Appium

### Athrun(TMTS)

### UIAutomator


## 安全

### 服务器安全

### 通信安全

### 数据加密

### 数据验签

### 代码混淆

### webview/JS安全调用

### MD5、DES、RSA、https、证书、权限
- [https](https://juejin.im/entry/5b5fc811f265da0f697049c1)
http三次握手 四次挥手


## NDK

### JNI

### C语言

### C++

- 引用于指针

- 智能指针

- 虚函数

## 手机功能

### 电话
- 联系人
- 通话记录

### 短/彩信

### Camera

### Audio

### SD卡

### 感应器
- 加速
- 方向
- 重力
- 光线
- 陀螺仪
- 磁场
- 距离
- 温度
- 压力
- 线性加速度
- 旋转
- 多点触控

## 第三方扩展

### 地图

### 语音识别

### 支付

### 统计分析

### 广告


## 插件化

### VirtualAPK

...


## 其他

### Intent

### AIDL

### wifi

### 国际化

### PopuWindow