jdk，jvm,jre区别
jdk java development kit 负责java编译
java 运行java文件
javac 编译java文件
jar 给java程序打包
javadoc 从java源码中提取注释并生成文档
jdb java调试器
jre java running environment，运行java虚拟机
jvm java virtual machine，识别class字节码文件并调用操作系统API，（跨平台的根本原因）

jvm架构
![JVM架构](https://github.com/sanyang176/archive/blob/main/Java/Java%E5%9F%BA%E7%A1%80/Images/jvm-image.png)
栈区：存储局部变量
堆区：存储对象
方法区：存储静态变量，静态方法，常量，字节码代码片段（各个线程共享内存区域），
寄存器（程序计数器）：存储指令地址。顺序执行时，存储下一条指令的地址，如果跳转到别的函数，会志向跳转函数的地址
本地方法栈：调用其它语言的native方法，比如java调c++

类加载器：双亲委派机制
![双亲委派机制](https://github.com/sanyang176/archive/blob/main/Java/Java%E5%9F%BA%E7%A1%80/Images/jvm-%E5%8F%8C%E4%BA%B2%E5%A7%94%E6%B4%BE.png)
具体内容：
java在加载类时，会逐级向上委托，直到找到启动类加载器，
启动类加载器主要加载java.lang等核心类库
扩展类加载器主要加载lib/ext中的外部库
应用程序类加载器加载用户类路径下面的类
最后到用户自定义的类加载器

jvm调优内容
1、-Xms2g：初始化推大小为 2g；

2、-Xmx2g：堆最大内存为 2g；

3、-XX:NewRatio=4：设置年轻的和老年代的内存比例为 1:4；

4、-XX:SurvivorRatio=8：设置新生代 Eden 和 Survivor 比例为 8:2；

5、–XX:+UseParNewGC：指定使用 ParNew + Serial Old 垃圾回收器组合；

6、-XX:+UseParallelOldGC：指定使用 ParNew + ParNew Old 垃圾回收器组合；

7、-XX:+UseConcMarkSweepGC：指定使用 CMS + Serial Old 垃圾回收器组合；

8、-XX:+PrintGC：开启打印 gc 信息；

9、-XX:+PrintGCDetails：打印 gc 详细信息；

10、-XX:+HeapDumpOnOutOfMemoryError：当JVM发生OOM时,自动生成DUMP文件。

