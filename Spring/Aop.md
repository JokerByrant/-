## Spring是什么？
> Spring是一个库，它的功能是提供了一个软件框架，这个框架的目的是使软件之间的逻辑更加清晰，配置更加灵活，实现这个目的的手段是IOC和AOP。

## OOP概念
**OOP(Object Oriented Programming)面向对象编程**OOP主要是为了实现编程的重用性、灵活性和扩展性。它的几个特征分别是**继承、封装、多态和抽象**。OOP重点体现在编程架构，强调的是类之间的层次关系。**但在使用OOP进行编程时，经常会出现一些相似的代码，这些内容大量重复**，使代码变的非常的臃肿。类似这样的情况同样会出现在我们编程中的很多地方，例如：**日志记录、性能统计、安全控制、事务处理、异常处理**等等。

## AOP概念
**AOP（面向切面编程），Aspect Oriented Programming的缩写，是一种可以通过预编译方式和运行期动态代理实现在不修改源代码的情况下给程序动态统一添加功能的一种技术。AOP主要作用是将代码切分为多个不同的代码块，将日志管理层、业务层分割开来。

## AOP应用场景
**AOP用来封装横切关注点，具体可以在下面的场景中使用：**
* **Authentication 权限**
* **Caching 缓存** 
* **Context passing 内容传递**
* Error handling 错误处理 
* Lazy loading 懒加载 
* Debugging 调试 
* logging, tracing, profiling and monitoring 记录跟踪 优化 校准 
* Performance optimization 性能优化 
* Persistence 持久化 
* Resource pooling 资源池 
* Synchronization 同步 
* **Transactions 事务**

## AOP和OOP关系
**OOP针对业务处理过程的实体（Dog、Cat、Duck）及其属性和行为（run）进行抽象封装，以获得更加清晰高效的逻辑单元划分。而AOP则是针对业务处理过程中（run或jump）的切面（command和award）进行提取，它所面对的是处理过程中的某个步骤或阶段，以获得逻辑过程中各部分之间低耦合性的隔离效果。**

