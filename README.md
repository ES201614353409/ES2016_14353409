![mahua](mahua-logo.jpg)
#DOL
##Description
分布式操作层（DOL）是一个软件开发框架编程并行应用程序。DOL允许指定的基础上计算的卡恩过程网络模型应用程序和功能的基础上的SystemC模拟引擎。此外，DOL提供了一个基于XML的规范格式来描述在一个多处理器系统，包括绑定和映射并行应用程序的执行。
#Install
###Ubuntu并配置好必要的环境

$ sudo apt-get update

$ sudo apt-get install ant

$ sudo apt-get install openjdk-7-jdk

$ sudo apt-get install unzip

###下载文件

$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz

$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

###解压文件

1.新建dol文件

$ mkdir dol 2.将dolethz.zip解压到 dol文件夹中

$ unzip dol_ethz.zip -d dol 3.解压systemc

$ tar -zxvf systemc-2.3.1.tgz

###编译systemc

1.解压后进入systemc-2.3.1的目录下

$ cd systemc-2.3.1 2.新建一个临时文件夹objdir

$ mkdir objdir 3.进入该文件夹objdir

$ cd objdir 4.运行configure（能根据系统的环境设置一下参数，用于编译）

$ ../configure CXX=g++ --disable-async-updates

###5.编译

$ sudo make install

6.记录当前的工作路径（会输出当前所在路径，记下来，待会有用）

$ pwd

###编译DOL

1.进入刚刚的dol文件夹，修改build.xml文件 找到下面这段话，就是说上面编译的systemc位置在哪里

property name=”systemc.inc” value=”YYY/include” property name=”systemc.lib” value=”YYY/lib-linux/libsystemc.a”/ 把YYY改成上页pwd的结果（注意，对于 64位 系统的机器，lib-linux要改成lib-linux64）

2.编译

$ ant -f build_zip.xml all 若成功会显示build sucessful

3.运行第一个例子进入build/bin/main路径下

$ cd build/bin/main

4.然后运行第一个例子

$ ant -f runexample.xml -Dnumber=1

##Experimental experience
本次的实验时DOL的配置实验，ta都给出了所有的操作步骤，我们只需要进行傻瓜式的操作就行了，总体上不是很难。就是在实验最后修改build.xml文件的时候，我的虚拟机是64位的，可是修改的时候需要将里面的信息改为32位的才能得到最终结果。这个也是后来问ta才知道的，被卡了很长时间。总的来说此次的实验是圆满的，收获巨大。