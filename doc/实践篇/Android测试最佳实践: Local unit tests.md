Local unit tests运行于JVM之上, 这部分测试并不能测试Android framework里面的功能。

#一 本地单元测试流程

##1.1 构建测试环境

当我们新建一个Android工程, Android Studio会自动创建Local unit tests与Instrumented tests，它们分别位于：
```
module-name/src/test/java/.
module-name/src/androidTest/java/.
```
Local unit tests：运行与本地JVM环境中，它并没有涉及Android Framework里的API。

Instrumented tests：运行在Android真实设备或者模拟器上。

接下来我们在Module的build.gradle里添加依赖:
```
dependencies {
    // Required -- JUnit 4 framework
    testCompile 'junit:junit:4.12'
    // Optional -- Mockito framework
    testCompile 'org.mockito:mockito-core:1.10.19'
}
```

##1.2 创建一个本地单元测试类

本地单元测试类应该按照JUnit4的测试类的写法来写, 最新的JUnit4可以让你写出更加清晰和灵活的单元测试, 不同于JUnit3的单元测试, 使用JUnit4, 你不需要继承junit.framework.TestCase类。
你也不需要在你的测试方法前添加test关键字，也不需要使用任何junit.framework或者是 junit.extensions包中的类。

为了创建一个基本的JUnit 4测试类，你需要创建一个java类，它包含一个或者多个测试方法。 一个测试方法使用@Test注解开始，同时包含你要测试和检验的单个功能的代码。

