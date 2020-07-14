design-patterns
主要参考：

[图说设计模式]: https://design-patterns.readthedocs.io/zh_CN/latest/	"图说设计模式"


[toc]
# 面向对象设计模式的六大原则

1. 开闭原则（Open Close Principle）

    开闭原则的意思是：对扩展开放，对修改关闭。在程序需要进行拓展的时候，不能去修改原有的代码，实现一个热插拔的效果。简言之，是为了使程序的扩展性好，易于维护和升级。想要达到这样的效果，我们需要使用接口和抽象类，后面的具体设计中我们会提到这点。

1. 里氏代换原则（Liskov Substitution Principle）

	里氏代换原则是面向对象设计的基本原则之一。 里氏代换原则中说，任何基类可以出现的地方，子类一定可以出现。LSP 是继承复用的基石，只有当派生类可以替换掉基类，且软件单位的功能不受到影响时，基类才能真正被复用，而派生类也能够在基类的基础上增加新的行为。里氏代换原则是对开闭原则的补充。实现开闭原则的关键步骤就是抽象化，而基类与子类的继承关系就是抽象化的具体实现，所以里氏代换原则是对实现抽象化的具体步骤的规范。

1. 依赖倒转原则（Dependence Inversion Principle）

	 这个原则是开闭原则的基础，具体内容：针对接口编程，依赖于抽象而不依赖于具体。

1. 接口隔离原则（Interface Segregation Principle）

	 这个原则的意思是：使用多个隔离的接口，比使用单个接口要好。它还有另外一个意思是：降低类之间的耦合度。由此可见，其实设计模式就是从大型软件架构出发、便于升级和维护的软件设计思想，它强调降低依赖，降低耦合。

1. 迪米特法则，又称最少知道原则（Demeter Principle）

	 最少知道原则是指：一个实体应当尽量少地与其他实体之间发生相互作用，使得系统功能模块相对独立。

1. 合成复用原则（Composite Reuse Principle）

    合成复用原则是指：尽量使用对象组合、聚合、关联，而不是继承来达到复用的目的。

    **PS**：有些资料，没有“合成复用原则”而是“单一职责原则”

1. 单一职责原则(Single-Responsibility Principle )：

	 1.  一个对象应该只包含单一的职责，并且该职责被完整地封装在一个类中
	 1. 就一个类而言，应该仅有一个引起它变化的原因。 
	
	 
	
	 
	
	 
# 创建型模式

创建型模式(Creational Pattern)对类的实例化过程进行了抽象，能够将软件模块中对象的创建和对象的使用分离。为了使软件的结构更加清晰，外界对于这些对象只需要知道它们共同的接口，而不清楚其具体的实现细节，使整个系统的设计更加符合单一职责原则。

创建型模式在创建什么(What)，由谁创建(Who)，何时创建(When)等方面都为软件设计者提供了尽可能大的灵活性。创建型模式隐藏了类的实例的创建细节，通过隐藏对象如何被创建和组合在一起达到使整个系统独立的目的。

**包含模式**

- 简单工厂模式（Simple Factory）

  重要程度：4 （5为满分）

- 工厂方法模式（Factory Method）

  重要程度：5

- 抽象工厂模式（Abstract Factory）

  重要程度：5

- 建造者模式（Builder）

  重要程度：2

- 原型模式（Prototype）

  重要程度：3

- 单例模式（Singleton）

  重要程度：4

## 1. 简单工厂模式4
### 简单工厂模式的主要优缺点
1. 简单工厂模式最大的优点在于实现对象的创建和对象的使用分离，将对象的创建交给专门的工厂类负责，
2. 但是其最大的缺点在于工厂类不够灵活，增加新的具体产品需要修改工厂类的判断逻辑代码（违反开闭原则），而且产品较多时，工厂方法代码将会非常复杂。
### 简单工厂模式的应用场景
1. 简单工厂模式适用情况包括：工厂类负责创建的对象比较少；客户端只知道传入工厂类的参数，对于如何创建对象不关心。
## 2. 工厂方法模式5
### 工厂模式的主要优缺点：
1. 工厂方法模式的主要优点是增加新的产品类时无须修改现有系统，并封装了产品对象的创建细节，系统具有良好的灵活性和可扩展性；
2. 其缺点在于增加新产品的同时需要增加新的工厂，导致系统类的个数成对增加，在一定程度上增加了系统的复杂性。

### 工厂模式的主要应用场景
1. 工厂方法模式适用情况包括：一个类不知道它所需要的对象的类；一个类通过其子类来指定创建哪个对象；将创建对象的任务委托给多个工厂子类中的某一个，客户端在使用时可以无须关心是哪一个工厂子类创建产品子类，需要时再动态指定。

## 3. 抽象工厂模式5
### 抽象工厂模式的主要优缺点：
1. 抽象工厂模式的主要优点是隔离了具体类的生成，使得客户并不需要知道什么被创建，而且每次可以通过具体工厂类创建一个产品族中的多个对象，增加或者替换产品族比较方便，增加新的具体工厂和产品族很方便；
2. 主要缺点在于增加新的产品等级结构很复杂，需要修改抽象工厂和所有的具体工厂类，对“开闭原则”的支持呈现倾斜性。

### 抽象工厂模式的主要应用场景
1. 抽象工厂模式适用情况包括：一个系统不应当依赖于产品类实例如何被创建、组合和表达的细节；系统中有多于一个的产品族，而每次只使用其中某一产品族；属于同一个产品族的产品将在一起使用；系统提供一个产品类的库，所有的产品以同样的接口出现，从而使客户端不依赖于具体实现。

## 4. 原型模式3

> 参考：https://www.cnblogs.com/haizai/p/12404326.html

### 浅拷贝的介绍

1）对于数据类型是基本数据类的成员变量，浅拷贝会直接进行值传递，也就是将该属性值复制一份给新的对象。
2）对于数据类型是引用数据类型的成员变量，比如说成员变量是某个数组、某个类的对象等，那么浅拷贝会进行引用传递，也就是只是将该成员变量的引用值（内存地址）复制一份给新的对象。因为实际上两对象的该成员变量都指向同一个实例。在这种情况下，在一个对象中修改该成员变量会影响到另一个对象的该成员变量值
3）前面的克隆羊是浅拷贝
4）浅拷贝是使用默认的clone（）方法来实现
sheep = (Sheep)supper.clone();

### 深拷贝基本介绍

1）复制对象的所有基本数据类型的成员变量值
2）为所有引用数据类型的成员变量申请存储空间，并复制每个引用数据类型成员变量所引用的对象，直到该对象可达的所有对象。也就是说，对象进行深拷贝要对整个对象进行拷贝
3）深拷贝实现方式1 ：重写clone方法来实现深拷贝
4）深拷贝实现方式2 ：通过对象序列化实现深拷贝

### 原型模式的主要应用场景

大体上有两种使用场景

1. 在需要一个类的大量对象的时候，使用原型模式是最佳选择，因为原型模式是在内存中对这个对象进行拷贝，要比直接new这个对象性能要好很多，在这种情况下，需要的对象越多，原型模式体现出的优点越明显。

2. 如果一个对象的初始化需要很多其他对象的数据准备或其他资源的繁琐计算，那么可以使用原型模式。

3. 当需要一个对象的大量公共信息，少量字段进行个性化设置的时候，也可以使用原型模式拷贝出现有对象的副本进行加工处理。

注：原型模式的拷贝是从内存（堆内存）中以二进制流的方式进行拷贝，重新分配一个内存块，并不会执行任何构造函数。

## 5. 单例模式4

### 单例模式的主要优缺点：

1. 单例模式的主要优点在于提供了对唯一实例的受控访问并可以节约系统资源；
2. 其主要缺点在于因为缺少抽象层而难以扩展，且单例类职责过重。

### 单例模式的主要应用场景

1. 系统只需要一个实例对象；客户调用类的单个实例只允许使用一个公共访问点。（一个具有自动编号主键的表可以有多个用户同时使用，但数据库中只能有一个地方分配下一个主键编号，否则会出现主键重复，因此该主键编号生成器必须具备唯一性，可以通过单例模式来实现。）

# 结构型模式

结构型模式(Structural Pattern)描述如何将类或者对 象结合在一起形成更大的结构，就像搭积木，可以通过 简单积木的组合形成复杂的、功能更为强大的结构。

结构型模式可以分为**类结构型模式**和**对象结构型模式**：

- 类结构型模式关心类的组合，由多个类可以组合成一个更大的系统，在类结构型模式中一般只存在继承关系和实现关系。

- 对象结构型模式关心类与对象的组合，通过关联关系使得在一 个类中定义另一个类的实例对象，然后通过该对象调用其方法。 

  

根据“合成复用原则”，在系统中尽量使用**关联关系**来替代**继承**关系，因此大部分结构型模式都是**对象结构型模式**。

**包含模式**

- 适配器模式(Adapter)

  重要程度：4

- 桥接模式(Bridge)

  重要程度：3

- 组合模式(Composite)

  重要程度：4

- 装饰模式(Decorator)

  重要程度：3

- 外观模式(Facade)

  重要程度：5

- 享元模式(Flyweight)

  重要程度：1

- 代理模式(Proxy)

  重要程度：4

## 1. 适配器模式4

### 适配器模式的主要优缺点

1. 适配器模式的主要优点是将目标类和适配者类解耦，增加了类的透明性和复用性，同时系统的灵活性和扩展性都非常好，更换适配器或者增加新的适配器都非常方便，符合“开闭原则”；
2. 类适配器模式的缺点是适配器类在很多编程语言中不能同时适配多个适配者类，对象适配器模式的缺点是很难置换适配者类的方法。

### 适配器模式的主要应用场景

1. 适配器模式适用情况包括：系统需要使用现有的类，而这些类的接口不符合系统的需要；想要建立一个可以重复使用的类，用于与一些彼此之间没有太大关联的一些类一起工作

### 实例：

Sun公司在1996年公开了Java语言的数据库连接工具JDBC，JDBC使得Java语言程序能够与数据库连接，并使用SQL语言来查询和操作数据。JDBC给出一个客户端通用的抽象接口，每一个具体数据库引擎（如SQL Server、Oracle、MySQL等）的JDBC驱动软件都是一个介于JDBC接口和数据库引擎接口之间的适配器软件。抽象的JDBC接口和各个数据库引擎API之间都需要相应的适配器软件，这就是为各个不同数据库引擎准备的驱动程序。

## 2. 桥接模式3

### 桥接模式的主要优缺点

1. 桥接模式的主要优点是分离抽象接口及其实现部分，是比多继承方案更好的解决方法，桥接模式还提高了系统的可扩充性，在两个变化维度中任意扩展一个维度，都不需要修改原有系统，实现细节对**客户**透明，可以对**用户**隐藏实现细节；
2. 其主要缺点是增加系统的理解与设计难度，且识别出系统中两个独立变化的维度并不是一件容易的事情。

### 桥接模式的主要应用场景

1. 需要在构件的抽象化角色和具体化角色之间增加更多的灵活性，避免在两个层次之间建立静态的继承联系；抽象化角色和实现化角色可以以继承的方式独立扩展而互不影响；一个类存在两个独立变化的维度，且这两个维度都需要进行扩展；设计要求需要独立管理抽象化角色和具体化角色；不希望使用继承或因为多层次继承导致系统类的个数急剧增加的系统。

### 桥接模式实例：

如果需要开发一个跨平台视频播放器，可以在不同操作系统平台（如Windows、Linux、Unix等）上播放多种格式的视频文件，常见的视频格式包括MPEG、RMVB、AVI、WMV等。现使用桥接模式设计该播放器。

## 3. 组合模式4

组合模式的实现根据所实现的接口的区别分为两种形式，分别称为**安全式**和**透明式**。

### 组合模式的主要优点有：

1. 组合模式使得客户端代码可以一致地处理单个对象和组合对象，无须关心自己处理的是单个对象，还是组合对象，这简化了客户端代码；
2. 更容易在组合体内加入新的对象，客户端不会因为加入了新的对象而更改源代码，满足“开闭原则”；

### 组合模式的主要应用场景

这种组合模式正是应树形结构而生，所以组合模式的使用场景就是出现树形结构的地方。比如：文件目录显示，多及目录呈现等树形结构数据的操作。

### 两种实现方式的选择

**这里所说的安全式组成模式是指：**从客户端使用组成模式上看是否更安全，如果是安全的，那么就不会有发生误操作的可能，能访问的方法都是被支持的。
 **这里所说的透明性组成模式是指：**从客户端使用组成模式上，是否需要区分到底是“树枝对象”还是“树叶对象”。如果是透明的，那就不用区分，对于客户而言，都是`Component`对象，具体的类型对于客户端而言是透明的，是无需关心的。

对于组合模式而言，在安全性和透明性上，会**更看重透明性**，毕竟组合模式的目的是：让客户端不再区分操作的是树枝对象还是树叶对象，而是以一个统一的方式来操作。

而且对于安全性的实现，需要区分的是树枝对象还是树叶对象。有时候，需要将对象进行类型转换，却发现类型信息丢失了，只好强行转换，这种类型转换必然是不够安全的。

因此在使用组合模式的时候，建议多采用透明式的实现方式。

## 4. 装饰模式3TODO

## 5. 外观模式5

## 6. 享元模式1

## 7. 代理模式4

# 行为型模式

行为型模式(Behavioral Pattern)是对在不同的对象之间划分责任和算法的抽象化。

行为型模式不仅仅关注类和对象的结构，而且重点关注它们之间的相互作用。

通过行为型模式，可以更加清晰地划分类与对象的职责，并研究系统在运行时实例对象 之间的交互。在系统运行时，对象并不是孤立的，它们可以通过相互通信与协作完成某些复杂功能，一个对象在运行时也将影响到其他对象的运行。

行为型模式分为类行为型模式和对象行为型模式两种：

- 类行为型模式：类的行为型模式使用继承关系在几个类之间分配行为，类行为型模式主要通过多态等方式来分配父类与子类的职责。
- 对象行为型模式：对象的行为型模式则使用对象的聚合关联关系来分配行为，对象行为型模式主要是通过对象关联等方式来分配两个或多个类的职责。根据“合成复用原则”，系统中要尽量使用关联关系来取代继承关系，因此大部分行为型设计模式都属于**对象行为型设计模式**。

**包含模式**

- 职责链模式(Chain of Responsibility)

  重要程度：3

- 命令模式(Command)

  重要程度：4

- 解释器模式(Interpreter)

  重要程度：1

- 迭代器模式(Iterator)

  重要程度：5

- 中介者模式(Mediator)

  重要程度：2

- 备忘录模式(Memento)

  重要程度：2

- 观察者模式(Observer)

  重要程度：5

- 状态模式(State)

  重要程度：3

- 策略模式(Strategy)

  重要程度：4

- 模板方法模式(Template Method)

  重要程度：3

- 访问者模式(Visitor)

  重要程度：1

## 1. 职责链模式3

## 2. 命令模式4

## 3. 解释器模式1

## 4. 迭代器模式5

## 5. 中介者模式2

## 6. 备忘录模式2

## 7.  观察者模式5

## 8. 状态模式3

## 9. 策略模式4

## 10. 模板方法模式3

## 11. 访问者模式1





# FAQ

## 1. 关于为什么使用工厂模式，而不是直接new
目前我的理解主要由两点：
1. 降低代码复杂度：工厂模式下，**不仅仅只有实例化功能，**可以对new的对象进行一些其他操作，比如工厂类创建的圆形，可以添加一些额外的设置，圆的名称，圆的颜色等（这里只是简单举例，有些可能涉及复杂的操作，比如计算设置圆的周长，面积）：**组合优先于继承相比于继承，我们更优先使用组合**——对于组合的好处，可以参考“状态模式(State Pattern)”，一个类可能需要非常多的组件，工厂模式可以降低使用者的代码复杂度和理解难度
2. 根据DP（迪米特法则）其实调用者并不知道有一个Circle类的存在，他只需要知道这个IShape接口可以计算圆面积，而不需要知道；圆这个类到底是什么类名——他只知道给定一个”circle"字符串的参数,IShape接口可以自动计算圆的面积就可以了！

## 2. 抽象工厂模式和工厂模式的区别
1. 抽象工厂模式与工厂方法模式最大的区别在于，工厂方法模式针对的是一个产品等级结构，而抽象工厂模式则需要面对多个产品等级结构。

