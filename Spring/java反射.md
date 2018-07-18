# 反射是框架设计的灵魂
> **使用的前提：必须先获取到相应字节码文件对应的Class类型的对象**

## 概念
> 在java程序的运行过程中，对于任何一个类，都能知道这个类的所有属性和方法，并且对于任何一个对象，
都能够调用它的任意一个方法和属性。**反射就是把java类中的各种成分映射成一个个的java对象**

## 反射的使用
### 使用步骤
* 获取想要操作的类的Class对象
* 获取该对象的属性、方法或构造方法
* 创建对象

### 获取Class对象的方式
```java
  //第一种
  Student stu = new Student();
  Class test1 = stu.getClass();
  
  //第二种
  Class test2 = Student.class;
  
  //第三种(最常用，建议使用)
  Class test3 = Class.forName("Studnet");
```
> **在运行期间，一个类，只有一个Class对象产生**

### 获取构造方法
* 批量的方法：
      public Constructor[] getConstructors()：所有"公有的"构造方法
      public Constructor[] getDeclaredConstructors()：获取所有的构造方法(包括私有、受保护、默认、公有)
     
* 获取单个的方法，并调用：
      public Constructor getConstructor(Class... parameterTypes):获取单个的"公有的"构造方法：
      public Constructor getDeclaredConstructor(Class... parameterTypes):获取"某个构造方法"可以是私有的，或受保护、默认、公有；

### 获取成员变量
* 批量的
 		1).Field[] getFields():获取所有的"公有字段"
  	2).Field[] getDeclaredFields():获取所有字段，包括：私有、受保护、默认、公有；
* 获取单个的：
  	1).public Field getField(String fieldName):获取某个"公有的"字段；
		2).public Field getDeclaredField(String fieldName):获取某个字段(可以是私有的)
  
* 设置字段的值：
**Field --> public void set(Object obj,Object value):**
  * 参数说明：
    * obj:要设置的字段所在的对象；
  	* value:要为字段设置的值；
    
### 获取成员方法
* m = stuClass.getDeclaredMethod("show4", int.class);//调用制定方法（所有包括私有的），需要传入两个参数，第一个是调用的方法名称，第二个是方法的形参类型，切记是类型。
* System.out.println(m);
* m.setAccessible(true);//解除私有限定
* Object result = m.invoke(obj, 20);//需要两个参数，一个是要调用的对象（获取有反射），一个是实参
* System.out.println("返回值：" + result);//

### 创建对象
**当我们获取到所需类的Class对象后，可以用它来创建对象，创建对象的方法有两种：**

* 使用Class对象的newInstance()方法来创建该Class对象对应类的实例，**但是这种方法要求该Class对象对应的类有默认的空构造器**。
* 先使用Class对象获取指定的Constructor对象，再调用Constructor对象的newInstance()方法来创建 Class对象对应类的实例,通过这种方法可以选定构造方法创建实例。

## 总结
反射就是在程序的运行状态时，对于任何一个类都能够知道这个类的属性和方法，并且对于任何一个对象都能调用它的任何一个属性或者方法。
Spring的DI技术（依赖注入）的原理就是java的反射机制，根据给出的需要注入的类名来匹配xml文件已初始化的bean，并将数据注入到指定的对象中。
