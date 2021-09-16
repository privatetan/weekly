## SPI思想

### 1、什么是SPI？

SPI，即服务供给接口（Service Provider Interface）；

SPI，是一种“面向接口编程”的思想；

SPI，通过事先定义的接口来找到其所有的接口实现类（服务），而后通过反射逐个实例化对象。



### 2、SPI与API

首先理解三个名词：调用者（Invoker）、接口（Interface）、提供者（Provider）；

```
调用者：Invoker，即接口调用者；

接口：Interface，即接口；

提供者：Provider，即接口实现者。
```

API：当接口属于提供者时，即提供者提供了接口定义和实现，让调用者使用接口来达到调用某实现类的功能，将其称为API；

SPI：当接口属于调用者时，即调用者提供了接口的定义，让提供者实现接口的功能以供调用者使用，将其称为SPI。

简言之：API，是以提供者提供接口标准；SPI，是以调用者提供接口标准。



### 3、Java中的SPI

##### JDK的SPI--ServiceLoader

ServiceLoader是实现SPI一个重要的类。是JDK1.6引进的一个特性。

在资源目录META-INF/services中放置提供者配置文件，然后程序运行时，使用Serviceloader.load(XxxInterface.class)，会到META-INF/services的配置文件中寻找这个接口对应的实现类全路径名，然后使用反射去生成一个无参的实例。

[使用参考，点击这里](https://www.jianshu.com/p/7601ba434ff4)

##### JDBC实现--java.sql.Driver

打开mysql-connector-java的jar包，在META-INF/services下会有com.mysql.jdbc.Driver文件，以供Java程序调用。





### 参考文章

Java SPI思想梳理 https://zhuanlan.zhihu.com/p/28909673



