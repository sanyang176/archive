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
