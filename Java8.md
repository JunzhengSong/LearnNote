## 函数式编程-Stream流

### Lambda表达式

lambda表达式只关注参数和方法体

基本格式

````java
（参数列表）-.{代码}
````

 例一

```java
//匿名内部类
new Thread(new Runnable()){
    @override
    public void run(){
        System.out.pringln("xxx")；
    }
}.start();
//labmda表达式
new Thread(()->{
    Sysem.out.println("xxx");
}).start();   
```

例二

```java

```







### Strea m流

流表示包含着一系列元素的集合，我们可以对其做不同类型的操作，用来对这些元素执行计算。

```java
List<String> myList =
    Arrays.asList("a1", "a2", "b1", "c2", "c1");

myList
    .stream() // 创建流
    .filter(s -> s.startsWith("c")) // 执行过滤，过滤出以 c 为前缀的字符串
    .map(String::toUpperCase) // 转换成大写
    .sorted() // 排序
    .forEach(System.out::println); // for 循环打印


```

可以对流进行中间操作或者终端操作

![Stream中间操作，终端操作](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2019/4/25/16a52771d4587e64~tplv-t2oaga2asx-jj-mark:3024:0:0:0:q75.awebp)

**①**：中间操作会再次返回一个流，所以，我们可以链接多个中间操作，注意这里是不用加分号的。上图中的`filter` 过滤，`map` 对象转换，`sorted` 排序，就属于中间操作。

**②**：终端操作是对流操作的一个结束动作，一般返回 `void` 或者一个非流的结果。上图中的 `forEach`循环 就是一个终止操作。





## 函数式编程





## 匿名内部类

匿名内部类是一种在使用时定义类的方式，通常用于创建只需使用一次的类。

匿名内部类允许在使用时定义和实例化一个类，而不必显式地为其创建一个独立的类文件。这使得代码更加紧凑和易读，尤其是在需要一个简单的类来执行特定任务的情况下。



## StreamAPI





## 接口

###  Comparable & Comparator



### Callable



## 注解

###  @FunctionalInterface

函数式接口FunctionalInterface是有且仅有一个抽象方法，但是可以有多个非抽象方法的接口，函数式接口可以被隐式转换为lambda表达式。







