## 装饰模式（Decorator）也叫包装器模式（Wrapper）

https://images2015.cnblogs.com/blog/1020480/201611/1020480-20161122203917206-859119829.png

![img](https://images2015.cnblogs.com/blog/1020480/201611/1020480-20161122203917206-859119829.png)

##### 用途：允许想一个现有的对象添加新功能（方法），同事又不改变其结构。  是增加，不是改变，能够级联增加（嵌套）

```
        System.out.println("增加两个新的功能，飞行，水里游");
        WaterCar waterCar2 = new WaterCar(new FlyCar(car));
        waterCar2.move();
```

实现：

1.创建一个含有功能（方法）的接口，让其继承

2.给他创建一个兄弟（实现功能接口），并且拥有并构造他（构造方法传接口类）

3.他的侄子可以把他包装（装饰）了

eg：

1. public interface  Action {  pblic move(); }
2. 他自己还是可能要改一些代码的，得实现这个接口（implyment）,或许可以从现有实现的接口里面加功能（有点不合规矩）。装饰器没有代理模式牛逼。





#### 观察者模式（又被称为发布-订阅（Publish/Subscribe）模式，属于行为型模式的一种

**是被观察者拥有观察者**，

1.抽象观察者（接口或父类）  Observer

2.具体观察者     Concre

3.抽象被观察者（接口）

4.具体被观察者

![图 6-11 观察者模式的结构图](https://img-blog.csdn.net/20161111191040882)