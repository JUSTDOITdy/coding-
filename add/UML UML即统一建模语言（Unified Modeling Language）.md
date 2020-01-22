UML UML即统一建模语言（Unified Modeling Language） 

UML类与类(接口)的关系，类与类（接口）一共有如下6种关系： 组合>聚合>关联>依赖 

泛化（继承）（Generalization）、空心三角形的直线 

实现（接口）（Realization）、  空心三角形的虚线 

依赖（SSM，把你定义成我的属性，使用你）（Dependence）、箭头的虚线，【构造函数的形参】

关联（Association）、比依赖更紧密 【类的成员变量】

聚合（Aggregation）、整体和部分的关系，   聚合用带空心菱形的直线表示，其中菱形指向整体 |

组合（Composition） 强调整体与部分的关系，不同的是部分无法脱离整体存在  带实心的菱形直线表示，其中菱形指向整体

![img](https://upload-images.jianshu.io/upload_images/2799767-3f16972d7b062110.png?imageMogr2/auto-orient/strip)

虚线箭头指向**依赖**；

实线箭头指向**关联**；

虚线三角指向**接口**；

实线三角指向**父类**；

空心菱形能分离而独立存在，是**聚合**；

实心菱形精密关联不可分，是**组合**；