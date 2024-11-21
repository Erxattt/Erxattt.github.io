---
title: Java基础
date: 2024-10-28 16:18:20
tags: [java]
categories: [后端]
feature: /img/java/java-basic.jpg

toc: true
---

## 一、基本语法

### 1. **Java 基本程序结构**

一个典型的 Java 程序结构如下：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- `class`：所有 Java 代码都在类中，`HelloWorld` 是类的名称。
- `main` 方法：这是程序的入口点，所有 Java 程序从 `main` 方法开始执行。
- `System.out.println`：用于输出信息到控制台。

### 2. **数据类型**

Java 是强类型语言，所有的变量都必须有确定的数据类型。Java 的数据类型分为两大类：**基本数据类型**和**引用数据类型**。

#### 2.1 基本数据类型

Java 提供了 8 种基本数据类型：

| 数据类型  | 大小（位） | 范围                  | 默认值   |
| --------- | ---------- | --------------------- | -------- |
| `byte`    | 8          | -128 到 127           | 0        |
| `short`   | 16         | -32,768 到 32,767     | 0        |
| `int`     | 32         | -2^31 到 2^31-1       | 0        |
| `long`    | 64         | -2^63 到 2^63-1       | 0L       |
| `float`   | 32         | IEEE 754 单精度浮点数 | 0.0f     |
| `double`  | 64         | IEEE 754 双精度浮点数 | 0.0d     |
| `char`    | 16         | 单一 Unicode 字符     | '\u0000' |
| `boolean` | 1 位       | `true` 或 `false`     | `false`  |

#### 2.2 引用数据类型

引用数据类型包括类、接口和数组：

- **类**：对象的蓝图或模板，如 `String`、`ArrayList` 等。
- **接口**：定义了类可以实现的一组方法。
- **数组**：一组相同类型的数据的集合。

### 3. **变量**

变量是用于存储数据的内存位置。声明变量的语法如下：

```java
数据类型 变量名 = 初始值;
```

例如：

```java
int age = 25;
String name = "John";
```

Java 中的变量类型可以分为以下三类：

#### 3.1 局部变量

局部变量在方法内部声明并使用，方法执行完毕后会被销毁。局部变量没有默认值，必须初始化。

```java
public void printAge() {
    int age = 25;  // 局部变量
    System.out.println(age);
}
```

#### 3.2 实例变量

实例变量属于对象，每个对象都有自己独立的实例变量。它们在类中声明，但在方法外部。

```java
public class Person {
    String name;  // 实例变量
    int age;
}
```

#### 3.3 静态变量

静态变量属于类，而不是对象，所有对象共享同一个静态变量。使用 `static` 关键字定义。

```java
public class Person {
    static int population = 100;  // 静态变量
}
```

### 4. **运算符**

Java 支持各种运算符用于处理数据。主要有以下几类：

#### 4.1 算术运算符

用于执行常见的数学运算，如加、减、乘、除等。

| 运算符 | 描述 |
| ------ | ---- |
| `+`    | 加法 |
| `-`    | 减法 |
| `*`    | 乘法 |
| `/`    | 除法 |
| `%`    | 取余 |

#### 4.2 关系运算符

用于比较两个值，结果为 `true` 或 `false`。

| 运算符 | 描述       |
| ------ | ---------- |
| `==`   | 等于       |
| `!=`   | 不等于     |
| `>`    | 大于       |
| `<`    | 小于       |
| `>=`   | 大于或等于 |
| `<=`   | 小于或等于 |

#### 4.3 逻辑运算符

用于连接多个条件表达式。

| 运算符 | 描述   |
| ------ | ------ |
| `&&`   | 逻辑与 |
| `!`    | 逻辑非 |

#### 4.4 赋值运算符

用于给变量赋值。

| 运算符 | 描述     |
| ------ | -------- |
| `=`    | 赋值     |
| `+=`   | 加并赋值 |
| `-=`   | 减并赋值 |
| `*=`   | 乘并赋值 |
| `/=`   | 除并赋值 |

### 5. **控制流语句**

Java 提供了多种控制流语句来控制程序的执行流程。

#### 5.1 条件语句

- `if-else` 语句：用于根据条件执行不同的代码块。

```java
if (age >= 18) {
    System.out.println("You are an adult.");
} else {
    System.out.println("You are not an adult.");
}
```

- `switch` 语句：根据变量的值选择要执行的代码块。

```java
int day = 2;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other day");
}
```

#### 5.2 循环语句

- `for` 循环：用于固定次数的循环。

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

- `while` 循环：根据条件重复执行代码块。

```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

- `do-while` 循环：至少执行一次，之后根据条件判断是否继续执行。

```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 5);
```

#### 5.3 `break` 和 `continue`

- `break`：跳出循环。
- `continue`：跳过当前循环，进入下一次循环。

## 二、面向对象编程

### 1. **类与对象**

#### 1.1 类的定义

**类** 是对象的模板或蓝图，它定义了对象的属性和方法。在 Java 中，类通过 `class` 关键字来定义。

```java
public class Person {
    String name;
    int age;

    public void sayHello() {
        System.out.println("Hello, my name is " + name);
    }
}
```

在这个例子中，`Person` 是一个类，它有两个属性 `name` 和 `age`，以及一个方法 `sayHello()`，用于输出问候语。

#### 1.2 对象的创建

**对象** 是类的实例，通过 `new` 关键字来创建。

```java
Person person = new Person();
person.name = "John";
person.age = 25;
person.sayHello();
```

在这个代码片段中，我们通过 `new` 关键字创建了一个 `Person` 对象 `person`，并访问其属性和方法。

#### 1.3 构造方法

**构造方法** 是在创建对象时自动调用的特殊方法，用于初始化对象的状态。构造方法与类同名，且没有返回类型。

```java
public class Person {
    String name;
    int age;

    // 构造方法
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void sayHello() {
        System.out.println("Hello, my name is " + name);
    }
}

Person person = new Person("John", 25);
person.sayHello();
```

#### 1.4 对象的属性和方法

- **属性（字段）**：对象的状态或数据，通过类中的变量定义。
- **方法**：操作对象行为的函数，用于对对象进行操作。

类中定义的属性和方法通过对象来访问。

### 2. **封装**

**封装** 是将对象的状态（属性）私有化，隐藏对象的实现细节，并提供公共方法来访问和修改属性。封装可以通过访问修饰符来实现。

#### 2.1 访问修饰符

Java 提供了四种访问修饰符，用于控制类、属性和方法的访问范围：

| 访问修饰符  | 说明                                                 |
| ----------- | ---------------------------------------------------- |
| `public`    | 对所有类可见。                                       |
| `private`   | 仅对当前类可见。                                     |
| `protected` | 对同一包和子类可见。                                 |
| `default`   | 没有显式的修饰符时，默认为包级访问，仅对同一包可见。 |

#### 2.2 Getter 和 Setter 方法

为了遵循封装原则，类的属性通常设置为 `private`，通过 `getter` 和 `setter` 方法来访问和修改这些属性。

```java
public class Person {
    private String name;
    private int age;

    // Getter 方法
    public String getName() {
        return name;
    }

    // Setter 方法
    public void setName(String name) {
        this.name = name;
    }
}
```

这样可以防止外部直接修改属性，保证了数据的安全性和完整性。

### 3. **继承**

**继承** 是面向对象编程中最重要的概念之一，它允许一个类从另一个类继承属性和方法，从而实现代码重用。通过继承，子类可以继承父类的行为，并可以对其进行扩展或修改。

#### 3.1 `extends` 关键字

使用 `extends` 关键字实现类的继承，子类继承父类的所有非私有的属性和方法。

```java
public class Animal {
    public void eat() {
        System.out.println("Animal is eating");
    }
}

public class Dog extends Animal {
    public void bark() {
        System.out.println("Dog is barking");
    }
}

Dog dog = new Dog();
dog.eat();  // 子类继承父类的方法
dog.bark(); // 子类自己的方法
```

#### 3.2 方法重写（Override）

**方法重写** 是指子类对父类的某个方法进行重新定义，使用相同的方法名、参数和返回类型。

```java
public class Animal {
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

public class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

Dog dog = new Dog();
dog.sound();  // 输出 "Dog barks"
```

#### 3.3 `super` 关键字

`super` 关键字 用于调用父类的方法或构造函数，常用于在子类重写方法时调用父类的版本。

```java
public class Animal {
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

public class Dog extends Animal {
    @Override
    public void sound() {
        super.sound();  // 调用父类的 sound 方法
        System.out.println("Dog barks");
    }
}
```

---

### 4. **多态**

**多态** 是指同一方法在不同对象中的不同表现形式。多态分为**编译时多态（方法重载）和运行时多态（方法重写）**。

#### 4.1 方法的重载（Overloading）

**方法重载** 是在同一个类中定义多个方法，它们有相同的方法名但参数不同，编译器会根据调用时的参数选择正确的方法执行。

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}
```

#### 4.2 方法的重写（Overriding）

**方法重写** 是指子类重新定义父类的某个方法，子类的版本将覆盖父类的版本。

### 5. **接口和抽象类**

#### 5.1 抽象类

**抽象类** 是无法实例化的类，它包含一个或多个抽象方法（没有具体实现的方法）。抽象类用于定义子类的公共行为。

```java
abstract class Animal {
    abstract void sound();
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```

#### 5.2 接口

**接口** 是一种比抽象类更抽象的类，接口中的所有方法默认都是 `public` 和 `abstract`，接口用于定义某种能力或行为，类可以实现一个或多个接口。

```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Dog barks");
    }
}
```

#### 5.3 区别与应用场景

##### 5.3.1 **接口和抽象类的主要区别**

| 特性           | 接口（`Interface`）                                                                     | 抽象类（`Abstract Class`）                          |
| -------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------- |
| 实现方式       | 一个类可以实现多个接口                                                                  | 一个类只能继承一个抽象类                            |
| 访问修饰符     | 接口中的方法默认是 `public`，无法定义 `private` 或 `protected`                          | 抽象类的成员可以是 `private`、`protected`、`public` |
| 方法的具体实现 | Java 8 之前，接口中的方法没有实现。Java 8 之后，接口可以包含 `default` 和 `static` 方法 | 抽象类中可以有方法的具体实现，也可以有抽象方法      |
| 适用场景       | 用于定义功能契约，不关心具体实现                                                        | 用于表示类的继承关系，适用于抽象类的行为扩展        |
| 构造函数       | 接口不能有构造函数                                                                      | 抽象类可以有构造函数                                |
| 成员变量       | 接口中只能有常量（`static final` 修饰）                                                 | 抽象类可以有普通成员变量                            |
| 使用场景       | 适合定义不同类之间的共同行为，如 "能力"                                                 | 适合描述类之间的继承关系，强调 "是什么"             |

##### 5.3.2 **选择的基本原则**

- **接口**：当你想要定义一组不相关类的**行为**时，应该使用接口。接口定义了一些通用的能力或功能，任何实现该接口的类都必须具备这些行为，但实现方式可能各不相同。
- **抽象类**：当你有一个公共基类，并希望多个子类共享相同的行为或属性时，应该使用抽象类。抽象类可以提供部分实现，子类可以继承这些实现并对其进行扩展。

##### 5.3.3 接口使用场景：定义能力

如果你需要定义一组不同类型的对象都可以拥有的功能，比如“飞行能力”，不同种类的飞行物（鸟、飞机、超人）可以实现飞行功能，但它们彼此之间没有继承关系。

```java
// 定义一个接口，表示"飞行"这个能力
public interface Flyable {
    void fly();
}

// 鸟类实现了Flyable接口
public class Bird implements Flyable {
    @Override
    public void fly() {
        System.out.println("Bird flaps its wings to fly");
    }
}

// 飞机类也实现了Flyable接口
public class Airplane implements Flyable {
    @Override
    public void fly() {
        System.out.println("Airplane uses engines to fly");
    }
}

// 超人类也实现了Flyable接口
public class Superman implements Flyable {
    @Override
    public void fly() {
        System.out.println("Superman flies with superpowers");
    }
}
```

在这个例子中，`Flyable` 定义了一个能力，即“飞行”，而 `Bird`、`Airplane` 和 `Superman` 类都实现了这个接口，它们拥有相同的行为（`fly` 方法），但各自的实现方式不同。

**使用接口的原因**：这些类之间并没有什么共性，它们的行为方式完全不同，但它们都具备某种相同的功能（飞行）。接口正好适用于这种“行为契约”的场景。

##### 5.3.4 抽象类使用场景：定义通用的基类

当你有一组类存在继承关系，且它们具有公共的属性或方法时，使用抽象类。例如，你有一组动物类，它们都有某些共同的行为和属性（如呼吸、移动），但某些行为需要子类去具体实现（如发声）。

```java
// 抽象类 Animal，定义通用的属性和行为
public abstract class Animal {
    String name;

    // 构造方法
    public Animal(String name) {
        this.name = name;
    }

    // 通用的方法
    public void breathe() {
        System.out.println(name + " is breathing");
    }

    // 抽象方法，具体由子类实现
    public abstract void makeSound();
}

// 狗类继承 Animal，必须实现 makeSound 方法
public class Dog extends Animal {
    public Dog(String name) {
        super(name);
    }

    @Override
    public void makeSound() {
        System.out.println(name + " says: Woof Woof");
    }
}

// 猫类继承 Animal，必须实现 makeSound 方法
public class Cat extends Animal {
    public Cat(String name) {
        super(name);
    }

    @Override
    public void makeSound() {
        System.out.println(name + " says: Meow Meow");
    }
}
```

在这个例子中，`Animal` 是一个抽象类，它有一个普通方法 `breathe()`，所有继承 `Animal` 的类都可以直接使用。而 `makeSound()` 是一个抽象方法，必须由子类来实现具体的发声方式。

**使用抽象类的原因**：所有的子类都是动物（`Animal`），它们有共同的特性，比如呼吸（`breathe` 方法），但每种动物发声的方式不同（`makeSound` 方法）。抽象类帮助我们避免在每个子类中重复定义通用的行为，同时允许子类根据具体需求定义特殊行为。

#### 5.4 **总结**

##### 5.4.1 **何时使用接口：**

- 当你需要为一组不相关的类提供某些功能时（如“飞行”、“游泳”等能力），使用接口。
- 接口可以帮助你定义**行为契约**，让不同的类通过实现相同的接口，具备相同的功能。

##### 5.4.2 **何时使用抽象类：**

- 当你有一组相关类，它们共享某些共同的行为和属性（如所有动物都会呼吸，但发声方式不同），使用抽象类。
- 抽象类可以帮助你在子类之间共享通用的代码，实现部分功能，让子类继承并扩展这些功能。

通过理解接口和抽象类的差异以及如何在具体场景中应用它们，可以更好地设计出灵活且可扩展的 Java 程序。

### 6. **包（Package）和导入（Import）**

#### 6.1 包（Package）

**包** 是用来组织类的机制，用于防止类名冲突和控制访问权限。通过 `package` 关键字声明类所在的包。

```java
package com.example;
public class Person {
    ...
}
```

#### 6.2 导入（Import）

`import` 语句 用于导入其他包中的类，以便在当前类中使用。

```java
import java.util.List;
```

## 三、异常处理

### 1.异常的类型

Java 中的异常是程序执行中出现的意外事件，分为**受检查异常**和**非受检查异常**两大类：

- **受检查异常（Checked Exception）**:编译阶段必须处理的异常，不处理编译都没法通过。
  - **非受检查异常（Unchecked Exception）**：运行时异常，不强制要求处理，通常是由于代码逻辑错误导致的。这类继承<code>RuntimeException</code>,例如：<code>NullPointerException</code>,<code>ArrayIndexOutOfBoundsException</code>等。

此外，还有**错误（Error）**，表示系统级别的，程序无法处理。例如：<code>OutOfMemoryError</code>、<code>StackOverflowError</code>。

### 2.异常处理机制

- `try`：用于包围可能发生异常的代码块。

- `catch`：捕获并处理在`try`块中抛出的异常。

- `finally`：无论是否发生异常，`finally`块中的代码都会执行，常用于资源的释放。

- `throw`：显式地抛出异常。

- `throws`：用于声明一个方法可能抛出的异常，提醒调用方需要处理。

### 3.基本语法

```java
try {
    // 可能发生异常的代码
} catch (ExceptionType1 e1) {
    // 处理 ExceptionType1 的异常
} catch (ExceptionType2 e2) {
    // 处理 ExceptionType2 的异常
} finally {
    // 无论是否发生异常，都会执行的代码
}
```

### 4.多异常捕获

java7 及以后，多个异常可以在一个 catch 里捕获

```java
try {
    // 可能发生异常的代码
} catch (IOException | SQLException e) {
    System.out.println("捕获到IO或SQL异常: " + e.getMessage());
}
```

### 5.<code>throw</code>和<code>throws</code>关键字

`throw`关键字：

用于显示的抛出一个异常

```java
public void checkAge(int age) {
    if (age < 18) {
        throw new IllegalArgumentException("年龄必须大于18岁");
    }
}
```

`throws`关键字：

用于声明一个方法体里可能抛出的异常，不处理，让调用者去处理

```java
public void readFile(String filePath) throws IOException {
    FileReader fileReader = new FileReader(filePath);
}
```

### 6.自定义异常

Java 允许你定义自己的异常类，通常自定义异常类继承自`Exception`或`RuntimeException`。例如：

```java
// 自定义的受检查异常
public class AgeException extends Exception {
    public AgeException(String message) {
        super(message);
    }
}

// 使用自定义异常
public void checkAge(int age) throws AgeException {
    if (age < 18) {
        throw new AgeException("年龄小于18，不允许操作");
    }
}
```

### 7.`finally`的作用

`finally`块用于释放资源或执行清理操作，它保证了无论是否发生异常，都能执行一些重要的操作，比如关闭文件流、释放数据库连接等。

```java
public void readFile(String filePath) {
    FileReader fileReader = null;
    try {
        fileReader = new FileReader(filePath);
        // 读取文件操作
    } catch (IOException e) {
        System.out.println("文件读取时发生异常: " + e.getMessage());
    } finally {
        if (fileReader != null) {
            try {
                fileReader.close();  // 释放资源
            } catch (IOException e) {
                System.out.println("文件关闭时发生异常: " + e.getMessage());
            }
        }
    }
}
```

### 8.`try-with-resources`语法

Java 7 引入了`try-with-resources`语法，简化了资源的关闭操作。实现`AutoCloseable`接口的资源可以在`try`块结束时自动关闭

```java
public void readFile(String filePath) {
    try (FileReader fileReader = new FileReader(filePath)) {
        // 读取文件操作
    } catch (IOException e) {
        System.out.println("文件读取时发生异常: " + e.getMessage());
    }
}
```

## 四、常用类

### 1. `Object` 类

- **描述**：`Object` 是所有类的父类，所有 Java 类都直接或间接继承自 `Object`。它提供了一些常用的基础方法。

- 常用方法

  ：

  - `toString()`：返回对象的字符串表示。
  - `equals(Object obj)`：判断两个对象是否相等。
  - `hashCode()`：返回对象的哈希码值。
  - `clone()`：创建并返回此对象的一个副本（浅拷贝）。
  - `finalize()`：在垃圾回收器回收对象时调用。

**示例**：

```java
Object obj1 = new Object();
Object obj2 = new Object();
System.out.println(obj1.equals(obj2));  // false
System.out.println(obj1.toString());    // 类似于 java.lang.Object@hashcode
```

---

### 2. `String` 类

- **描述**：`String` 类用于表示不可变的字符串，Java 中 `String` 对象是不可变的（每次修改都会创建新对象）。
- 常用方法：
  - `length()`：返回字符串的长度。
  - `charAt(int index)`：获取指定位置的字符。
  - `substring(int beginIndex, int endIndex)`：截取字符串的子串。
  - `contains(CharSequence s)`：判断字符串是否包含指定的子串。
  - `equals(Object obj)`：比较两个字符串是否相等。
  - `trim()`：去掉字符串前后的空格。
  - `replace(CharSequence target, CharSequence replacement)`：替换子串。

**示例**：

```java
String str = "Hello World";
System.out.println(str.length());                // 11
System.out.println(str.charAt(0));               // 'H'
System.out.println(str.substring(0, 5));         // "Hello"
System.out.println(str.contains("World"));       // true
System.out.println(str.replace("World", "Java")); // "Hello Java"
```

---

### 3. `StringBuilder` 和 `StringBuffer` 类

- **描述**：这两个类都用于创建可变的字符串，其中 `StringBuilder` 是非线程安全的，`StringBuffer` 是线程安全的（方法带有 `synchronized` 关键字）。
- 常用方法：
  - `append(String str)`：将字符串追加到当前对象末尾。
  - `insert(int offset, String str)`：在指定位置插入字符串。
  - `delete(int start, int end)`：删除子串。
  - `reverse()`：将字符串反转。

**示例**：

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb.toString());  // "Hello World"

sb.insert(5, ",");
System.out.println(sb.toString());  // "Hello, World"

sb.delete(5, 6);
System.out.println(sb.toString());  // "Hello World"

sb.reverse();
System.out.println(sb.toString());  // "dlroW olleH"
```

---

### 4. `Integer`、`Double` 等包装类

- **描述**：包装类用于将基本数据类型（如 `int`、`double` 等）封装为对象类型，使其可以用于需要对象的场景（如集合）。
- 常用方法：
  - `parseInt(String s)`：将字符串转换为 `int`。
  - `valueOf(String s)`：将字符串转换为对应的包装类对象。
  - `intValue()`：将包装类对象转换为基本类型 `int`。
  - `toString()`：将基本数据类型转换为字符串。

**示例**：

```java
String numStr = "100";
int num = Integer.parseInt(numStr);
System.out.println(num);  // 100

Integer numObj = Integer.valueOf(numStr);
System.out.println(numObj);  // 100
System.out.println(numObj.intValue());  // 100
```

---

### 5. `Math` 类

- **描述**：`Math` 类提供了用于数学运算的静态方法，如取整、三角函数、随机数生成等。
- 常用方法：
  - `abs(int a)`：返回绝对值。
  - `max(int a, int b)`：返回两个数中的较大值。
  - `pow(double a, double b)`：计算 a 的 b 次方。
  - `sqrt(double a)`：返回平方根。
  - `random()`：返回一个 `0.0` 到 `1.0` 之间的随机数。

**示例**：

```java
int absValue = Math.abs(-10);  // 10
double maxValue = Math.max(5.5, 10.2);  // 10.2
double powerValue = Math.pow(2, 3);  // 8.0
double sqrtValue = Math.sqrt(16);  // 4.0
double randomValue = Math.random();  // 介于0.0到1.0之间的随机数
```

---

### 6. `ArrayList` 类

- **描述**：`ArrayList` 是一个动态数组，支持动态扩展。它是 `List` 接口的实现类，常用于存储有序的元素列表。

- 常用方法

  ：

  - `add(E e)`：向列表中添加元素。
  - `get(int index)`：获取指定索引的元素。
  - `remove(int index)`：移除指定索引的元素。
  - `size()`：返回列表中元素的数量。
  - `contains(Object o)`：判断列表是否包含指定的元素。

**示例**：

```java
ArrayList<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
System.out.println(list.get(0));  // "Apple"
System.out.println(list.size());  // 2
list.remove(1);
System.out.println(list.size());  // 1
System.out.println(list.contains("Apple"));  // true
```

---

### 7. `HashMap` 类

- **描述**：`HashMap` 是基于哈希表的实现，用于存储键值对。它允许 `null` 键和 `null` 值，并且元素的顺序是不保证的。
- 常用方法：
  - `put(K key, V value)`：向映射中插入键值对。
  - `get(Object key)`：获取指定键对应的值。
  - `remove(Object key)`：移除指定键对应的键值对。
  - `containsKey(Object key)`：判断映射中是否包含指定的键。
  - `size()`：返回映射中键值对的数量。

**示例**：

```java
HashMap<String, Integer> map = new HashMap<>();
map.put("Apple", 1);
map.put("Banana", 2);
System.out.println(map.get("Apple"));  // 1
map.remove("Banana");
System.out.println(map.containsKey("Banana"));  // false
```

---

### 8. `Date` 和 `Calendar` 类

- **描述**：`Date` 类表示日期和时间，`Calendar` 类提供了对日期时间的更多操作和格式化功能。
- 常用方法：
  - `Date()`：创建当前日期对象。
  - `getTime()`：返回日期的时间戳。
  - `Calendar.getInstance()`：获取当前日期时间的 `Calendar` 实例。
  - `set(int field, int value)`：设置指定的日期字段。

**示例**：

```java
Date date = new Date();
System.out.println(date.getTime());  // 获取当前时间的时间戳

Calendar calendar = Calendar.getInstance();
calendar.set(Calendar.YEAR, 2024);
System.out.println(calendar.getTime());  // 修改年份并获取新的日期
```

---

### 9. `Scanner` 类

- **描述**：`Scanner` 类用于从控制台读取输入数据，支持读取字符串、整数、浮点数等。
- 常用方法：
  - `nextLine()`：读取一行输入。
  - `nextInt()`：读取一个整数。
  - `nextDouble()`：读取一个浮点数。

**示例**：

```java
Scanner scanner = new Scanner(System.in);
System.out.println("Enter your name: ");
String name = scanner.nextLine();
System.out.println("Your name is: " + name);

System.out.println("Enter your age: ");
int age = scanner.nextInt();
System.out.println("Your age is: " + age);
```

## 五、集合框架

java 集合框架是用于存储和操作一组数据的标准 API，提供了各种数据结构（如列表、集合、映射等），大大简化了数据操作。它定义了一组接口和实现类来管理数据元素的集合。掌握集合框架不仅能有效提高代码的性能和可读性，而且对解决实际问题也非常有帮助。接下来，我们将详细讲解集合框架的各个方面，包括其核心接口、常用实现类及其特点、遍历方式、线程安全问题等。

### 1. **集合框架的层次结构**

Java 集合框架的基本层次结构如下图：

```mathematica
                    Collection
                  /     |     \
              List     Set   Queue
               |        |      |
          ArrayList  HashSet  PriorityQueue
           LinkedList LinkedHashSet ArrayDeque
           Vector      TreeSet
           Stack

                    Map
                   /   \
              HashMap  TreeMap
              LinkedHashMap
              Hashtable
```

#### 1.1 `Collection` 接口

`Collection` 是集合框架的根接口，代表一组对象。它有三个主要子接口：

- `List`：元素有序且可以重复。
- `Set`：元素无序且不允许重复。
- `Queue`：用于按照特定顺序（如 FIFO）存储和处理元素。

#### 1.2 `Map` 接口

`Map` 并不继承 `Collection`，它是一种特殊的接口，用于存储键值对（`key-value`）的映射关系，允许通过键查找对应的值。

### 2. **核心接口与实现类**

#### 2.1 `List` 接口

`List` 是一种有序集合，允许重复元素。它可以通过索引访问元素，并保持元素的插入顺序。常见的实现类有：

- `ArrayList`：基于动态数组实现，支持随机访问，查询效率高，适合频繁读取数据的场景，但在插入或删除时，若涉及移动大量元素，则性能较低。

  **示例**：

  ```java
  List<String> list = new ArrayList<>();
  list.add("apple");
  list.add("banana");
  System.out.println(list.get(0));  // 输出 "apple"
  ```

- `LinkedList`：基于双向链表实现，插入和删除操作效率高，适合需要频繁插入或删除元素的场景。但随机访问效率低，需要遍历链表。

  **示例**：

  ```java
  java复制代码List<String> list = new LinkedList<>();
  list.add("apple");
  list.add("banana");
  System.out.println(list.get(1));  // 输出 "banana"
  ```

- `Vector`：与 `ArrayList` 类似，但它是线程安全的，所有方法都使用了 `synchronized` 关键字。由于其线程安全特性，性能较低。

- `Stack`：继承自 `Vector`，是一种后进先出（LIFO）的栈数据结构。`push()` 方法用于压栈，`pop()` 方法用于弹栈。

#### 2.2 `Set` 接口

`Set` 是一个不允许重复元素的集合。常见的实现类有：

- `HashSet`：基于哈希表实现，支持快速查找、插入和删除操作，但不保证元素的顺序。

  **示例**：

  ```java
  Set<String> set = new HashSet<>();
  set.add("apple");
  set.add("banana");
  set.add("apple");  // 重复元素将被忽略
  ```

- `LinkedHashSet`：继承自 `HashSet`，但它保持插入元素的顺序。

- `TreeSet`：基于红黑树实现，保证元素的自然顺序或通过 `Comparator` 提供的顺序。

#### 2.3 `Queue` 接口

`Queue` 用于按照特定顺序存储和处理元素，通常用于实现先进先出（FIFO）的队列。常见的实现类有：

- `PriorityQueue`：一种基于堆的数据结构，元素按照优先级排序，优先级高的元素最先出队。

  **示例**：

  ```java
  Queue<Integer> queue = new PriorityQueue<>();
  queue.offer(3);
  queue.offer(1);
  queue.offer(2);
  System.out.println(queue.poll());  // 输出 1，优先级最高
  ```

- `ArrayDeque`：一个双端队列，既可以作为栈使用，也可以作为队列使用。比 `LinkedList` 更高效。

#### 2.4 `Map` 接口

`Map` 用于存储键值对，键是唯一的，而值可以重复。常见的实现类有：

- `HashMap`：基于哈希表实现，允许 `null` 键和 `null` 值，不保证顺序。

  **示例**：

  ```java
  Map<String, Integer> map = new HashMap<>();
  map.put("apple", 1);
  map.put("banana", 2);
  System.out.println(map.get("apple"));  // 输出 1
  ```

- `LinkedHashMap`：继承自 `HashMap`，保持插入顺序或访问顺序。

- `TreeMap`：基于红黑树实现，按照键的自然顺序或 `Comparator` 提供的顺序排序。

- `Hashtable`：与 `HashMap` 类似，但它是线程安全的，性能相对较低。`Hashtable` 不允许 `null` 键和 `null` 值。

### 3. **遍历集合的方式**

Java 提供了多种遍历集合的方法：

#### 3.1 使用 `for-each` 循环

`for-each` 循环适用于遍历 `Collection` 类型的集合。

**示例**：

```java
List<String> list = new ArrayList<>();
list.add("apple");
list.add("banana");
for (String fruit : list) {
    System.out.println(fruit);
}
```

#### 3.2 使用迭代器 (`Iterator`)

`Iterator` 提供了遍历集合的标准方式，特别适合在遍历时需要删除元素的场景。

**示例**：

```java
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    String fruit = iterator.next();
    if (fruit.equals("banana")) {
        iterator.remove();
    }
}
```

#### 3.3 使用 `Stream API`

Java 8 引入的 `Stream API` 提供了函数式编程风格的遍历和操作集合的方法。

**示例**：

```java
list.stream().forEach(System.out::println);
```

### 4. **集合的线程安全**

在多线程环境中使用集合时，线程安全是一个需要重点考虑的问题。Java 提供了多种方式来保证集合的线程安全：

#### 4.1 同步集合

可以使用 `Collections.synchronizedXXX()` 方法将非线程安全的集合转换为线程安全的集合。

**示例**：

```java
List<String> syncList = Collections.synchronizedList(new ArrayList<>());
```

#### 4.2 并发集合

Java 5 引入了 `java.util.concurrent` 包，提供了一些高效的线程安全集合类：

- `ConcurrentHashMap`：高效的线程安全的哈希表，替代 `Hashtable`，避免全表锁定。
- `CopyOnWriteArrayList`：适用于读操作多、写操作少的场景，在写时复制。
- `BlockingQueue`：一种线程安全的队列，支持阻塞操作，用于生产者-消费者模型。

### 5. **常见问题与优化**

#### 5.1 **如何选择合适的集合**

选择合适的集合类可以提高程序的性能，以下是一些建议：

- **查询频繁**：选择 `ArrayList` 或 `HashMap`。
- **插入、删除频繁**：选择 `LinkedList` 或 `TreeSet`。
- **需要线程安全**：选择 `ConcurrentHashMap` 或 `CopyOnWriteArrayList`。

#### 5.2 如何避免 `ConcurrentModificationException`

当使用 `Iterator` 遍历集合时，如果集合在遍历过程中被修改（如插入或删除元素），会抛出 `ConcurrentModificationException`。可以通过以下方式避免：

- 使用 `Iterator.remove()` 方法删除元素，而不是直接使用集合的 `remove()`。
- 使用 `CopyOnWriteArrayList` 来避免遍历时修改导致的异常。

#### 5.3 **使用 Stream 优化集合操作**

在处理大量数据时，`Stream API` 可以简化代码并提供更好的性能。例如，可以通过并行流（`parallelStream()`）来利用多核处理器提升性能

## 六、多线程

多线程编程是计算机科学中并发编程的一个重要组成部分，它允许程序在同一时间执行多个操作或任务。Java 提供了丰富的多线程支持，通过线程的创建和管理，我们可以编写出高效的、多任务的程序。在深入讲解多线程之前，需要理解基本概念、Java 中线程的创建方式、线程之间的协作、常见问题以及高级线程编程的技巧。

### 1. **基本概念**

- **进程（Process）**：一个进程是一个程序的运行实例。每个进程都有自己的内存空间和资源，进程之间通常是相互隔离的。

- **线程（Thread）**：线程是进程中的一个执行路径，一个进程可以包含多个线程。线程共享进程的内存空间，但每个线程都有自己的栈、程序计数器和局部变量。

- **并行（Parallelism）**：多个线程同时在不同的 CPU 上运行，真正做到同时执行。

- **并发（Concurrency）**：多个线程看起来像是同时执行，实际上它们在共享 CPU 资源，通过时间片轮转实现。

### 2. **线程的生命周期**

线程的生命周期通常可以分为以下几个阶段：

1. **新建状态（New）**：线程被创建，但还没有开始执行。
2. **就绪状态（Runnable）**：线程已经准备好执行，等待 CPU 的调度。
3. **运行状态（Running）**：线程获得了 CPU 时间片，开始执行任务。
4. **阻塞状态（Blocked）**：线程等待某个条件或资源。
5. **终止状态（Terminated）**：线程完成了任务或者被强制中止。

### 3. **Java 中的线程创建方式**

在 Java 中，创建线程主要有以下两种方式：

#### 3.1 继承 `Thread` 类

通过继承 `Thread` 类并重写其 `run()` 方法来定义一个线程。

**示例**：

```java
class MyThread extends Thread {
    @Override
    public void run() {
        System.out.println("Thread is running.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start();  // 启动线程
    }
}
```

**说明**：

- `start()` 方法会调用线程的 `run()` 方法，创建新的线程并执行任务。
- 不能直接调用 `run()` 方法，否则会在主线程中运行，而不是创建新线程。

#### 3.2 实现 `Runnable` 接口

通过实现 `Runnable` 接口的 `run()` 方法并将其传递给 `Thread` 对象。

**示例**：

```java
class MyRunnable implements Runnable {
    @Override
    public void run() {
        System.out.println("Thread is running.");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start();  // 启动线程
    }
}
```

**说明**：

- 这种方式更灵活，因为可以让类继承其他类而同时实现多线程功能（Java 不支持多继承）。

#### 3.3 使用 Lambda 表达式

如果使用 Java 8 及以上版本，可以用 Lambda 简化实现。

**示例**：

```java
public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> System.out.println("Thread is running."));
        thread.start();
    }
}
```

#### 3.4 使用 `Executor` 框架

`Executor` 框架提供了一种高级的线程管理方式，可以动态分配线程池来管理线程。

**示例**：

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class Main {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(5);
        executor.execute(() -> System.out.println("Thread is running."));
        executor.shutdown();  // 关闭线程池
    }
}
```

**说明**：

- `Executor` 框架提供了灵活的线程管理方式，避免了直接管理线程的麻烦。

### 4. **线程之间的协作**

在多线程编程中，线程之间通常需要协调和通信，以确保共享资源的安全访问。Java 提供了几种常见的协作机制。

#### 4.1 `synchronized` 关键字

`sychronized` 关键字可以确保同一时间只有一个线程访问被保护的代码块或方法。它用于解决**线程安全**问题，防止多个线程同时访问共享资源。

**示例**：

```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();
        Thread t1 = new Thread(counter::increment);
        Thread t2 = new Thread(counter::increment);
        t1.start();
        t2.start();
        t1.join();
        t2.join();
        System.out.println(counter.getCount());
    }
}
```

**说明**：

- `synchronized` 确保同一时刻只有一个线程能够进入 `increment()` 方法。
- 使用 `join()` 方法确保主线程等待子线程执行完成。

#### 4.2 `wait()` 和 `notify()`

`wait()` 和 `notify()` 用于实现线程之间的通信。一个线程可以调用 `wait()` 方法等待条件满足，另一个线程可以调用 `notify()` 方法唤醒等待的线程。

**示例**：

```java
class Task {
    public synchronized void doTask() throws InterruptedException {
        System.out.println("Task is waiting.");
        wait();  // 当前线程等待
        System.out.println("Task is resumed.");
    }

    public synchronized void resumeTask() {
        notify();  // 唤醒等待中的线程
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException {
        Task task = new Task();

        Thread t1 = new Thread(() -> {
            try {
                task.doTask();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        });
        Thread t2 = new Thread(task::resumeTask);

        t1.start();
        Thread.sleep(1000);
        t2.start();
    }
}
```

**说明**：

- `wait()` 会让当前线程进入等待状态，直到其他线程调用 `notify()` 或 `notifyAll()`。
- `wait()` 和 `notify()` 必须在同步方法或同步块中调用。

---

### 5. **线程池**

线程池是一个事先创建好的线程集合，可以重复使用。使用线程池有助于提高性能并管理系统资源。

#### 5.1 `Executors` 创建线程池

`Executors` 提供了一些常用的线程池实现：

- `newFixedThreadPool(int n)`：创建一个固定大小的线程池。
- `newCachedThreadPool()`：创建一个可以根据需要创建新线程的线程池，但会重用以前的线程。
- `newSingleThreadExecutor()`：创建一个只有单个线程的线程池。

**示例**：

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class Main {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(3);

        for (int i = 0; i < 5; i++) {
            executor.execute(() -> System.out.println("Thread: " + Thread.currentThread().getName()));
        }

        executor.shutdown();
    }
}
```

**说明**：

- 线程池避免了频繁创建和销毁线程的开销。
- `shutdown()` 用于关闭线程池，不再接收新的任务，但会继续执行已提交的任务。

### 6. **常见多线程问题**

多线程编程容易引发一些问题，需要特别小心处理：

#### 6.1 **线程安全问题**

当多个线程同时访问和修改共享变量时，可能会出现**数据不一致**的问题。通常需要通过同步机制来保证线程安全。

#### 6.2 **死锁**

死锁是指两个或多个线程相互等待对方释放锁，导致程序无法继续执行。

**避免死锁的策略**：

- 避免嵌套锁定。
- 保证线程获取锁的顺序一致。

#### 6.3 **活锁**

活锁是指线程在不断做出响应，但由于某种条件未满足，任务无法完成。

#### 6.4 **饥饿**

饥饿是指某个线程由于无法获得足够的资源，导致其无法继续执行。

### 7. **高级多线程技术**

#### 7.1 `Lock` 接口

`Lock` 提供了比 `synchronized` 更加灵活的锁机制。`ReentrantLock` 是常用的 `Lock` 实现类，支持可重入锁定。

**示例**：

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

class MyLock {
    private Lock lock = new ReentrantLock();

    public void doSomething() {
        lock.lock();
        try {
            System.out.println("Thread " + Thread.currentThread().getName() + " is working");
        } finally {
            lock.unlock();
        }
    }
}
```

#### 7.2 `CountDownLatch`

`CountDownLatch` 是一种同步辅助类，它允许一个或多个线程等待，直到其他线程完成某些操作。

#### 7.3 `CyclicBarrier`

`CyclicBarrier` 允许一组线程互相等待，直到所有线程都达到某个共同点。

## 七、输入输出（IO）

在 Java 中，IO（输入/输出，Input/Output）操作是指程序与外部设备（如文件、网络、控制台等）进行数据交互的过程。Java 提供了丰富的类库来处理 IO 操作，主要位于 `java.io` 和 `java.nio` 包中。我们可以按照流（Stream）的概念来理解 IO 操作。

### 1. **IO 的基本概念**

Java 的 IO 操作以 **流（Stream）** 为中心，流是指数据的有序序列。根据数据的流动方向，流分为：

- **输入流（Input Stream）**：用于从外部读取数据。
- **输出流（Output Stream）**：用于向外部写出数据。

根据处理数据类型的不同，Java 中的流可以分为两类：

- 字节流（Byte Stream）：处理字节级别的输入和输出，主要用于处理二进制数据。
  - 输入字节流：`InputStream` 及其子类。
  - 输出字节流：`OutputStream` 及其子类。
- 字符流（Character Stream）：处理字符级别的输入和输出，主要用于处理文本数据。
  - 输入字符流：`Reader` 及其子类。
  - 输出字符流：`Writer` 及其子类。

### 2. **字节流**

#### 2.1 `InputStream` 类

`InputStream` 是字节输入流的基类，常见子类包括 `FileInputStream`、`BufferedInputStream`、`ByteArrayInputStream` 等。

**常用方法**：

- `int read()`：从输入流中读取一个字节，返回读取的字节数据（0~255），如果已到达流的末尾，则返回 -1。
- `int read(byte[] b)`：将数据读取到字节数组中，返回实际读取的字节数。
- `void close()`：关闭输入流，释放相关资源。

**示例**：

```java
FileInputStream fis = null;
try {
    fis = new FileInputStream("example.txt");
    int data;
    while ((data = fis.read()) != -1) {
        System.out.print((char) data);
    }
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (fis != null) {
        try {
            fis.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### 2.2 `OutputStream` 类

`OutputStream` 是字节输出流的基类，常见子类包括 `FileOutputStream`、`BufferedOutputStream`、`ByteArrayOutputStream` 等。

**常用方法**：

- `void write(int b)`：将一个字节写入输出流。
- `void write(byte[] b)`：将字节数组中的数据写入输出流。
- `void close()`：关闭输出流，释放相关资源。

**示例**：

```java
FileOutputStream fos = null;
try {
    fos = new FileOutputStream("output.txt");
    String content = "Hello, World!";
    fos.write(content.getBytes());
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (fos != null) {
        try {
            fos.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 3. **字符流**

字符流主要用于处理文本数据。与字节流不同，字符流会根据字符集（如 UTF-8、ISO-8859-1 等）对数据进行编码和解码。

#### 3.1 `Reader` 类

`Reader` 是字符输入流的基类，常见子类包括 `FileReader`、`BufferedReader`、`InputStreamReader` 等。

**常用方法**：

- `int read()`：读取单个字符。
- `int read(char[] cbuf)`：将数据读取到字符数组中，返回实际读取的字符数。
- `String readLine()`（仅限 `BufferedReader`）：读取一行文本。
- `void close()`：关闭输入流。

**示例**：

```java
BufferedReader reader = null;
try {
    reader = new BufferedReader(new FileReader("example.txt"));
    String line;
    while ((line = reader.readLine()) != null) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (reader != null) {
        try {
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### 3.2 `Writer` 类

`Writer` 是字符输出流的基类，常见子类包括 `FileWriter`、`BufferedWriter`、`OutputStreamWriter` 等。

**常用方法**：

- `void write(int c)`：写入单个字符。
- `void write(char[] cbuf)`：将字符数组中的数据写入输出流。
- `void write(String str)`：将字符串写入输出流。
- `void close()`：关闭输出流。

**示例**：

```java
BufferedWriter writer = null;
try {
    writer = new BufferedWriter(new FileWriter("output.txt"));
    writer.write("Hello, World!");
    writer.newLine();
    writer.write("Java IO is powerful.");
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (writer != null) {
        try {
            writer.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 4. **缓冲流**

缓冲流通过为输入和输出流提供缓冲区来提高读写效率。常见的缓冲流有：

- `BufferedInputStream` 和 `BufferedOutputStream`：为字节流提供缓冲。
- `BufferedReader` 和 `BufferedWriter`：为字符流提供缓冲。

**示例**（使用 `BufferedReader` 读取文件）：

```java
BufferedReader reader = new BufferedReader(new FileReader("example.txt"));
String line;
while ((line = reader.readLine()) != null) {
    System.out.println(line);
}
reader.close();
```

### 5. **转换流**

转换流用于在字节流和字符流之间进行转换。

- `InputStreamReader`：将 `InputStream` 转换为 `Reader`。
- `OutputStreamWriter`：将 `OutputStream` 转换为 `Writer`。

**示例**：

```java
InputStreamReader isr = new InputStreamReader(new FileInputStream("example.txt"), "UTF-8");
BufferedReader br = new BufferedReader(isr);
String line;
while ((line = br.readLine()) != null) {
    System.out.println(line);
}
br.close();
```

### 6. **序列化与反序列化**

Java 的序列化机制允许将对象保存为字节流或从字节流恢复对象。要实现序列化的类必须实现 `Serializable` 接口。

#### 6.1 **序列化**

使用 `ObjectOutputStream` 来将对象序列化为字节流。

**示例**：

```java
ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("object.dat"));
oos.writeObject(new Person("John", 30));
oos.close();
```

#### 6.2 **反序列化**

使用 `ObjectInputStream` 来从字节流恢复对象。

**示例**：

```java
ObjectInputStream ois = new ObjectInputStream(new FileInputStream("object.dat"));
Person person = (Person) ois.readObject();
ois.close();
```

### 7. **NIO（New IO）**

Java NIO 是 Java 1.4 引入的新 IO 库，具有更高的性能，特别适用于大数据传输和非阻塞 IO。主要概念有：

- **通道（Channel）**：类似于流，但具有更好的性能和双向性。
- **缓冲区（Buffer）**：用于与通道交互，存储读写的数据。
- **选择器（Selector）**：用于管理多个通道的事件（主要用于非阻塞 IO）。

#### 示例：使用 NIO 读取文件

```java
RandomAccessFile file = new RandomAccessFile("example.txt", "r");
FileChannel channel = file.getChannel();
ByteBuffer buffer = ByteBuffer.allocate(1024);
int bytesRead = channel.read(buffer);
while (bytesRead != -1) {
    buffer.flip();  // 切换为读模式
    while (buffer.hasRemaining()) {
        System.out.print((char) buffer.get());
    }
    buffer.clear();  // 清空缓冲区，继续读入
    bytesRead = channel.read(buffer);
}
channel.close();
file.close();
```

### **8. `File` 类**

`File` 类表示一个文件或目录的抽象路径名，提供了创建、删除、重命名文件和目录等基本操作，同时可以获取文件的属性（如大小、路径、是否可读等）。

`File` 类的常用操作有：

- 创建文件或目录。
- 删除文件或目录。
- 判断文件或目录是否存在。
- 获取文件的基本属性（如路径、大小等）。

#### **8.1 `File` 类的常用方法**

##### **8.1.1 文件和目录的操作**

- `boolean createNewFile()`：如果文件不存在，则创建新文件，返回 `true`；如果文件已存在，则返回 `false`。
- `boolean mkdir()`：创建目录（单层目录），如果目录已存在，则返回 `false`。
- `boolean mkdirs()`：创建目录（多层目录），如果目录已存在，则返回 `false`。
- `boolean delete()`：删除文件或目录。
- `boolean exists()`：判断文件或目录是否存在。
- `boolean isFile()`：判断路径是否是文件。
- `boolean isDirectory()`：判断路径是否是目录。

**示例**：

```java
File file = new File("example.txt");
if (!file.exists()) {
    try {
        file.createNewFile();  // 创建文件
        System.out.println("文件已创建");
    } catch (IOException e) {
        e.printStackTrace();
    }
} else {
    System.out.println("文件已存在");
}

File directory = new File("myDir");
if (!directory.exists()) {
    directory.mkdir();  // 创建目录
    System.out.println("目录已创建");
}
```

##### **8.1.2 获取文件和目录的信息**

- `String getName()`：获取文件或目录的名称。
- `String getPath()`：获取文件或目录的相对路径。
- `String getAbsolutePath()`：获取文件或目录的绝对路径。
- `long length()`：获取文件的大小（字节数），如果是目录则返回 0。
- `long lastModified()`：获取文件的最后修改时间，返回自 1970 年 1 月 1 日以来的毫秒数。

**示例**：

```java
File file = new File("example.txt");
if (file.exists()) {
    System.out.println("文件名: " + file.getName());
    System.out.println("相对路径: " + file.getPath());
    System.out.println("绝对路径: " + file.getAbsolutePath());
    System.out.println("文件大小: " + file.length() + " 字节");
    System.out.println("最后修改时间: " + new Date(file.lastModified()));
}
```

##### **8.1.3 文件的重命名**

- `boolean renameTo(File dest)`：将文件或目录重命名为指定的文件或目录，成功返回 `true`。

**示例**：

```
File oldFile = new File("example.txt");
File newFile = new File("new_example.txt");
if (oldFile.renameTo(newFile)) {
    System.out.println("文件重命名成功");
} else {
    System.out.println("文件重命名失败");
}
```

##### **8.1.4 列出目录中的文件和子目录**

- `String[] list()`：返回该目录下文件和目录的名称列表。
- `File[] listFiles()`：返回该目录下文件和目录的 `File` 对象列表。

**示例**：

```java
File directory = new File("myDir");
if (directory.isDirectory()) {
    String[] files = directory.list();  // 获取文件名列表
    for (String file : files) {
        System.out.println(file);
    }

    File[] fileList = directory.listFiles();  // 获取 File 对象列表
    for (File f : fileList) {
        System.out.println(f.getName());
    }
}
```

#### **8.2 递归遍历目录**

使用 `File` 类可以很方便地递归遍历目录中的所有文件和子目录。

**示例**：递归打印目录下的所有文件

```java
public static void listAllFiles(File dir) {
    if (dir.isDirectory()) {
        File[] files = dir.listFiles();
        if (files != null) {
            for (File file : files) {
                if (file.isDirectory()) {
                    listAllFiles(file);  // 递归调用
                } else {
                    System.out.println("文件: " + file.getAbsolutePath());
                }
            }
        }
    }
}

public static void main(String[] args) {
    File directory = new File("myDir");
    listAllFiles(directory);
}
```

#### **8.3 文件过滤器**

`File` 类还支持通过过滤器（`FileFilter` 和 `FilenameFilter` 接口）筛选目录下的文件。

##### **8.3.1 `FileFilter` 接口**

`FileFilter` 是一个函数式接口，只有一个方法 `boolean accept(File pathname)`，可以用来过滤文件。

**示例**：过滤 `.txt` 文件

```java
File directory = new File("myDir");
File[] txtFiles = directory.listFiles(new FileFilter() {
    @Override
    public boolean accept(File file) {
        return file.getName().endsWith(".txt");
    }
});
for (File file : txtFiles) {
    System.out.println(file.getName());
}
```

##### **8.3.2 `FilenameFilter` 接口**

`FilenameFilter` 接口也可以用于过滤文件，方法是 `boolean accept(File dir, String name)`。

**示例**：过滤 `.txt` 文件

```java
File directory = new File("myDir");
String[] txtFiles = directory.list(new FilenameFilter() {
    @Override
    public boolean accept(File dir, String name) {
        return name.endsWith(".txt");
    }
});
for (String fileName : txtFiles) {
    System.out.println(fileName);
}
```

#### **8.4 `File` 类总结**

- `File` 类主要用于表示和操作文件和目录，它可以用来检查文件是否存在、创建和删除文件、列出目录内容等。
- `File` 本身并不提供读写文件内容的功能，要读写文件需要使用 `InputStream`、`OutputStream`、`Reader` 和 `Writer` 类。

`File` 类是处理文件和目录的基础，在很多场景中，如文件管理、递归查找、过滤等都非常有用。如果需要操作文件内容，可以结合流类（如 `FileInputStream`、`FileReader`）进行使用。

### **9. `IOUtils` 工具类**

`IOUtils` 类是 Apache Commons IO 库中的一个工具类，提供了一些静态方法用于简化 Java 中的 I/O 操作。`IOUtils` 主要用于文件的读写、流的操作以及各种输入输出流的辅助功能，使得常见的 I/O 操作变得更加简洁和方便。

#### **9.1 依赖引入**

如果要使用 `IOUtils`，需要在项目中引入 Apache Commons IO 的依赖。如果是 Maven 项目，可以在 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>commons-io</groupId>
    <artifactId>commons-io</artifactId>
    <version>2.11.0</version> <!-- 请检查最新版本 -->
</dependency>
```

#### **9.2 常用方法**

##### **9.2.1 文件和流的读写**

- **读取文件内容**：

  ```java
  String content = IOUtils.toString(new FileInputStream("example.txt"), StandardCharsets.UTF_8);
  ```

- **将字符串写入文件**：

  ```java
  IOUtils.write("Hello, World!", new FileOutputStream("output.txt"), StandardCharsets.UTF_8);
  ```

##### **9.2.2 流的操作**

- **拷贝输入流到输出流**：

  ```java
  InputStream input = new FileInputStream("source.txt");
  OutputStream output = new FileOutputStream("destination.txt");
  IOUtils.copy(input, output);
  ```

- **关闭流**：在使用流的时候，通常需要手动关闭流，而 `IOUtils` 提供了 `closeQuietly` 方法来避免处理异常：

  ```java
  IOUtils.closeQuietly(input);
  IOUtils.closeQuietly(output);
  ```

##### **9.2.3 字节和字符流转换**

- **将输入流转换为字节数组**：

  ```java
  byte[] bytes = IOUtils.toByteArray(new FileInputStream("example.txt"));
  ```

- **将输入流转换为字符串**：

  ```java
  String content = IOUtils.toString(new FileInputStream("example.txt"), StandardCharsets.UTF_8);
  ```

#### **9.3 示例代码**

下面是一个使用 `IOUtils` 读取文件内容并写入另一个文件的示例：

```java
import org.apache.commons.io.IOUtils;
import java.io.*;

public class IOUtilsExample {
    public static void main(String[] args) {
        InputStream input = null;
        OutputStream output = null;
        try {
            input = new FileInputStream("source.txt");
            output = new FileOutputStream("destination.txt");
            IOUtils.copy(input, output);
            System.out.println("文件复制成功！");
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            IOUtils.closeQuietly(input);
            IOUtils.closeQuietly(output);
        }
    }
}
```

#### **9.4 总结**

- `IOUtils` 类提供了简单易用的方法来处理 Java 中的 I/O 操作，避免了大量的样板代码。
- 它的常用功能包括文件读写、流的复制和关闭等，非常适合日常开发中的文件处理需求。

使用 `IOUtils` 可以提高代码的可读性和维护性，使得文件和流的处理变得更加方便。

## 八、JVM 基础

JVM 内存结构：堆（Heap）、栈（Stack）、方法区（Method Area）、本地方法栈（Native Method Stack）。

类加载机制：双亲委派模型。

垃圾回收机制：引用计数法、标记-清除算法、标记-复制算法、分代回收机制。

JVM 调优：堆大小设置、垃圾回收器选择。

## 九、反射机制

### 1. **反射的基本概念**

**反射机制**允许我们在运行时获取任意类的结构信息，而不需要在**编译时明确地知道类的类型**。这意味着我们可以：

- 获取类的元数据（类名、修饰符、包名等）
- 获取类的构造方法、成员变量、方法
- 创建实例对象
- 调用方法、修改字段值

反射的核心是`Class`对象，每个 Java 类在编译时都会生成一个对应的`Class`对象。通过这个对象，我们可以获得该类的所有信息。

### 2. **获取 Class 对象**

在 Java 中，获取类的`Class`对象有以下几种方式：

1. **使用类的`Class.forName()`方法**：

   ```java
   Class<?> clazz = Class.forName("com.example.MyClass");
   ```

2. **通过类的`.class`属性**：

   ```java
   Class<?> clazz = MyClass.class;
   ```

3. **通过对象的`getClass()`方法**：

   ```java
   MyClass myObject = new MyClass();
   Class<?> clazz = myObject.getClass();
   ```

### 3. **反射的常见操作**

#### 3.1 **获取类的信息**

使用反射，我们可以获取类的基本信息，包括类的名字、修饰符、实现的接口、继承的父类等。

**示例：**

```java
Class<?> clazz = MyClass.class;

// 获取类名
System.out.println("类名: " + clazz.getName());

// 获取包名
System.out.println("包名: " + clazz.getPackage().getName());

// 获取修饰符
int modifiers = clazz.getModifiers();
System.out.println("是否是public类: " + Modifier.isPublic(modifiers));

// 获取父类
Class<?> superclass = clazz.getSuperclass();
System.out.println("父类: " + superclass.getName());

// 获取实现的接口
Class<?>[] interfaces = clazz.getInterfaces();
for (Class<?> iface : interfaces) {
    System.out.println("实现的接口: " + iface.getName());
}
```

#### 3.2 **获取构造方法**

通过反射可以获取类的所有构造方法，并可以动态调用构造方法来创建对象实例。

**示例：**

```java
Class<?> clazz = MyClass.class;

// 获取所有构造方法
Constructor<?>[] constructors = clazz.getDeclaredConstructors();
for (Constructor<?> constructor : constructors) {
    System.out.println("构造方法: " + constructor);
}

// 使用某个构造方法创建对象实例
Constructor<?> constructor = clazz.getConstructor(String.class);  // 获取单参数构造
Object obj = constructor.newInstance("Hello");
```

#### 3.3 **获取类的字段**

通过反射可以访问类的成员变量（字段），包括私有字段。

**示例：**

```java
Class<?> clazz = MyClass.class;

// 获取所有字段
Field[] fields = clazz.getDeclaredFields();
for (Field field : fields) {
    System.out.println("字段名: " + field.getName());
}

// 获取并修改某个字段的值
Object obj = clazz.newInstance();
Field field = clazz.getDeclaredField("name");
field.setAccessible(true);  // 允许访问私有字段
field.set(obj, "New Value");
System.out.println("修改后的字段值: " + field.get(obj));
```

#### 3.4 **获取类的方法**

通过反射可以获取类的所有方法，并且可以动态调用这些方法。

**示例：**

```java
java复制代码Class<?> clazz = MyClass.class;

// 获取所有方法
Method[] methods = clazz.getDeclaredMethods();
for (Method method : methods) {
    System.out.println("方法名: " + method.getName());
}

// 调用某个方法
Method method = clazz.getDeclaredMethod("sayHello", String.class);
method.setAccessible(true);  // 如果是私有方法需要设置为可访问
method.invoke(obj, "World");  // 动态调用方法
```

#### 3.5 **数组操作**

反射还可以用于操作数组，动态创建数组、获取数组长度、访问或修改数组元素。

**示例：**

```java
int[] array = (int[]) Array.newInstance(int.class, 5);  // 创建一个长度为 5 的 int 数组
Array.set(array, 0, 100);  // 设置数组的第一个元素
int value = (int) Array.get(array, 0);  // 获取数组的第一个元素
System.out.println("数组的第一个元素: " + value);
```

### 4. **反射的使用场景**

1. **框架设计**：如 Spring、Hibernate 等框架大量使用反射来进行依赖注入、AOP（面向切面编程）等动态代理操作。反射使得这些框架能够在运行时动态加载类、自动配置和创建对象。

2. **动态代理**：反射结合`java.lang.reflect.Proxy`可以实现 Java 动态代理，允许在运行时为某些接口创建代理对象。

3. **工具类和库**：反射广泛用于通用工具类，如 Bean 工具、ORM 框架等，用于将 Java 对象与数据库记录之间的映射。

4. **JVM 内部操作**：反射用于操作一些无法通过普通手段访问的 API 和类，如通过反射访问私有字段和方法等。

5. **动态加载类**：通过反射可以根据需求动态加载类和执行方法，减少依赖和耦合，尤其适合插件化开发。

### 5. **反射的性能影响**

反射在功能上非常灵活，但也带来了性能损耗。因为 Java 在运行时需要对类和方法进行解析和动态调用，与普通的直接调用相比效率较低。

**性能影响的原因：**

1. 反射跳过了编译时的类型检查和优化，增加了运行时开销。
2. 通过反射调用方法比直接调用需要更多的步骤，包括权限检查和方法查找。
3. 反射在访问私有字段和方法时需要设置`setAccessible(true)`，这也会增加一定的开销。

**性能优化建议**：

1. **尽量少用反射**：如果可以通过编译时确定类结构，尽量避免使用反射。
2. **缓存反射结果**：如果必须频繁使用反射，建议将反射操作的结果缓存起来，如通过`Method`或`Field`对象进行缓存，而不是每次重新获取类结构信息。

### 6. **反射的局限性**

1. **类型安全问题**：反射在运行时绕过了编译时的类型检查，可能会引发`ClassCastException`等类型安全问题。
2. **复杂性**：使用反射会增加代码的复杂性和难以维护性，尤其是在动态操作多个类和方法时，代码的可读性较差。
3. **访问控制问题**：虽然反射可以访问私有字段和方法，但这可能会破坏封装原则，容易导致安全隐患。
4. **编译器优化问题**：由于反射是在运行时确定类和方法，因此编译器无法进行静态优化，这使得反射的代码性能较差。

### 7. **反射与动态代理**

Java 反射与动态代理密切相关。**动态代理**允许程序在运行时为某些接口创建代理对象，拦截对接口方法的调用，并可以在调用前后插入自定义逻辑。

动态代理的核心依赖于反射，通过`InvocationHandler`和`Proxy.newProxyInstance()`可以创建动态代理对象。

**示例：**

```java
// 定义接口
public interface MyInterface {
    void doSomething();
}

// 实现接口的动态代理
MyInterface proxyInstance = (MyInterface) Proxy.newProxyInstance(
    MyInterface.class.getClassLoader(),
    new Class[]{MyInterface.class},
    (proxy, method, args) -> {
        System.out.println("方法 " + method.getName() + " 被调用");
        return null;
    }
);

// 调用代理方法
proxyInstance.doSomething();
```

## 十、注解

### 1. **注解的基本概念**

Java 的注解是一种**元数据**，用于描述代码中的类、方法、字段等元素。常见的注解有三种主要作用：

- **提供信息给编译器**：注解可以为编译器提供信息，如抑制警告、检查代码质量。
- **生成代码或文档**：通过注解处理器（Annotation Processor）生成额外的代码或文档。
- **在运行时动态处理**：通过反射在运行时读取注解，动态调整程序的行为

### 2. **内置注解**

Java 提供了一些常见的**内置注解**，如：

1. `@Override`：表示该方法重写了父类中的方法。

   ```java
   @Override
   public String toString() {
       return "MyClass";
   }
   ```

2. `@Deprecated`：标记某个方法、类、字段已经过时，建议不再使用。

   ```java
   @Deprecated
   public void oldMethod() {
       // 旧的方法
   }
   ```

3. `@SuppressWarnings`：用于抑制编译器产生的警告，如未使用的变量或未检查的类型转换。

   ```java
   @SuppressWarnings("unchecked")
   public void myMethod() {
       List list = new ArrayList();
       list.add("Hello");
   }
   ```

4. `@FunctionalInterface`：用于表示一个接口是函数式接口，只能有一个抽象方法。Lambda 表达式可以使用这样的接口。

   ```java
   @FunctionalInterface
   public interface MyFunction {
       void execute();
   }
   ```

### 3. **元注解**

Java 提供了用于定义注解的**元注解**（Meta-Annotation）。元注解用于描述其他注解的行为。

1. `@Retention`：定义注解的**保留策略**，决定注解在什么阶段被保留。它有三个值：

   - `RetentionPolicy.SOURCE`：注解只在源码中保留，编译后会被丢弃。
   - `RetentionPolicy.CLASS`：注解在编译时保留在类文件中，但 JVM 加载类时会忽略它（默认）。
   - `RetentionPolicy.RUNTIME`：注解在运行时也会被 JVM 保留，可以通过反射读取。

   ```java
   @Retention(RetentionPolicy.RUNTIME)
   public @interface MyAnnotation {
       String value();
   }
   ```

2. `@Target`：定义注解可以应用到的**元素**类型，如类、方法、字段等。常见的取值包括：

   - `ElementType.TYPE`：类、接口、枚举
   - `ElementType.FIELD`：字段
   - `ElementType.METHOD`：方法
   - `ElementType.PARAMETER`：方法参数
   - `ElementType.CONSTRUCTOR`：构造方法
   - `ElementType.ANNOTATION_TYPE`：注解类型

   ```java
   @Target(ElementType.METHOD)
   public @interface MyAnnotation {
       String value();
   }
   ```

3. `@Inherited`：表明某个注解可以被子类继承。默认情况下，注解不会被继承。

   ```java
   @Inherited
   @Retention(RetentionPolicy.RUNTIME)
   @Target(ElementType.TYPE)
   public @interface MyInheritedAnnotation {
   }
   ```

4. `@Documented`：表示注解可以出现在 Javadoc 中。

### 4. **自定义注解**

我们可以根据自己的需要创建**自定义注解**。自定义注解可以包含一些元素（类似于属性），并通过元注解来指定它的行为。

#### 4.1 创建一个简单的自定义注解

**示例**：

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface MyAnnotation {
    String value() default "defaultValue";  // 注解元素，带有默认值
}
```

#### 4.2 使用自定义注解

**示例**：

```java
public class MyClass {

    @MyAnnotation(value = "Custom Value")
    public void myMethod() {
        System.out.println("My Method");
    }
}
```

#### 4.3 通过反射读取自定义注解

为了在运行时读取注解，我们可以使用反射。

**示例**：

```java
java复制代码public class AnnotationProcessor {

    public static void main(String[] args) throws Exception {
        Method method = MyClass.class.getMethod("myMethod");

        if (method.isAnnotationPresent(MyAnnotation.class)) {
            MyAnnotation annotation = method.getAnnotation(MyAnnotation.class);
            System.out.println("注解值: " + annotation.value());
        }
    }
}
```

运行结果：

```makefile
注解值: Custom Value
```

### 5. **注解处理器（Annotation Processor）**

Java 提供了 `javax.annotation.processing` 包，用于编写注解处理器（Annotation Processor）。通过注解处理器，可以在编译期处理注解，生成代码、修改字节码或执行其他操作。

#### 5.1 基本注解处理器示例

```java
java复制代码@SupportedAnnotationTypes("MyAnnotation")
@SupportedSourceVersion(SourceVersion.RELEASE_8)
public class MyAnnotationProcessor extends AbstractProcessor {

    @Override
    public boolean process(Set<? extends TypeElement> annotations, RoundEnvironment roundEnv) {
        for (Element element : roundEnv.getElementsAnnotatedWith(MyAnnotation.class)) {
            System.out.println("Processing element: " + element.getSimpleName());
        }
        return true; // 表示注解已经处理
    }
}
```

## 十一、泛型

#### 1.泛型的基本概念

泛型的核心思想是允许在定义类、接口或方法时使用**类型参数**，这样可以在使用时再指定具体的类型。泛型最常用的场景就是集合类，如`List<T>`、`Map<K, V>`等。

示例：

```java
// 定义一个泛型类
public class Box<T> {
    private T value;

    public void set(T value) {
        this.value = value;
    }

    public T get() {
        return value;
    }
}

// 使用泛型类
Box<Integer> intBox = new Box<>();
intBox.set(123);
Integer value = intBox.get();  // 编译器自动检查类型
```

#### 2.**泛型的好处**

- **类型安全**：泛型可以在编译时检查类型一致性，避免类型转换错误。
- **代码复用**：通过泛型类和泛型方法，可以编写通用的代码，支持多种不同类型。
- **可读性**：泛型代码更具自描述性，读者可以直观地了解泛型参数的作用。

#### 3.**泛型类、接口和方法**

##### (1)泛型类

泛型类是在类定义时引入类型参数的类，可以用来操作各种类型的数据。

**示例：**

```java
public class Pair<K, V> {
    private K key;
    private V value;

    public Pair(K key, V value) {
        this.key = key;
        this.value = value;
    }

    public K getKey() { return key; }
    public V getValue() { return value; }
}

// 使用泛型类
Pair<String, Integer> pair = new Pair<>("Age", 30);
```

##### (2)泛型接口

泛型接口和泛型类类似，可以在接口定义时引入类型参数。

**示例：**

```java
public interface Container<T> {
    void add(T item);
    T remove();
}
```

##### (3)泛型方法

泛型方法可以让方法在定义时使用类型参数，不仅仅局限于泛型类或接口。

**示例：**

```java
public class Utils {
    // 泛型方法
    public static <T> void printArray(T[] array) {
        for (T item : array) {
            System.out.println(item);
        }
    }
}

// 调用泛型方法
String[] names = {"Tom", "Jerry"};
Utils.printArray(names);
```

#### 4.**泛型的边界（Bounded Type Parameters）**

有时我们希望限制泛型的类型范围，这就是**边界**。使用`extends`关键字，我们可以限定泛型的上界。

**示例：**

```java
// T 必须是 Number 类型或其子类型
public class Box<T extends Number> {
    private T value;

    public void set(T value) {
        this.value = value;
    }

    public T get() {
        return value;
    }
}

// 只能使用 Number 或其子类
Box<Integer> intBox = new Box<>();
Box<Double> doubleBox = new Box<>();
// Box<String> strBox = new Box<>(); // 编译错误，String 不是 Number 的子类
```

可以同时设置多个边界，用`&`分隔：

```java
<T extends Number & Comparable<T>>  // T 必须是 Number 的子类并且实现 Comparable 接口
```

#### 5.泛型的通配符（Wildcard）

Java 提供了**通配符**（Wildcard）机制来处理泛型的灵活性。通配符有以下几种情况：

##### 无界通配符（`<?>`）

表示可以接受任何类型的泛型，通常用于只读数据的场景。

**示例：**

```java
public void printList(List<?> list) {
    for (Object item : list) {
        System.out.println(item);
    }
}
```

`<?>` 表示这个方法可以接受任何类型的`List`，如`List<String>`、`List<Integer>`等。

##### 上界通配符（`<? extends T>`）

表示可以接受**T 或其子类**，通常用于读取操作，因为可以保证类型的安全性。

**示例：**

```java
public void processNumbers(List<? extends Number> numbers) {
    for (Number num : numbers) {
        System.out.println(num);
    }
}
```

这里`List<? extends Number>`可以接受`List<Integer>`、`List<Double>`等。

##### 下界通配符（`<? super T>`）

表示可以接受**T 或其父类**，通常用于写操作，因为写入时需要保证类型的安全性。

**示例：**

```java
public void addNumbers(List<? super Integer> list) {
    list.add(1);
    list.add(2);
}
```

这里`List<? super Integer>`可以接受`List<Integer>`、`List<Number>`、`List<Object>`等。

## 十二、网络编程

`Socket`、`ServerSocket`、`DatagramSocket`进行 TCP 和 UDP 编程。

URL 与 Http 请求处理。

## 十三、Java8 新特性

Java 8 是 Java 平台上最重要的一次版本更新之一，带来了许多新的特性和增强功能。这些新特性不仅提升了编程的灵活性和表达能力，还极大地改善了代码的简洁性和可读性。下面是 Java 8 中的一些主要新特性：

### 1.**Lambda 表达式**

Lambda 表达式是 Java 8 中最具代表性的新特性之一，它允许使用更简洁的方式表示匿名函数，简化了代码编写，特别是在处理集合和函数式接口时

**语法：**

```java
(parameters) -> expression
```

**示例：**

```java
// 原来的匿名内部类写法
new Thread(new Runnable() {
    @Override
    public void run() {
        System.out.println("Hello World");
    }
}).start();

// 使用Lambda表达式
new Thread(() -> System.out.println("Hello World")).start();
```

### 2.**函数式接口（Functional Interfaces）**

Java 8 引入了**函数式接口**的概念，一个函数式接口是指仅包含一个抽象方法的接口。虽然早在 Java 之前就有类似的接口（如`Runnable`、`Comparator`等），但 Java 8 为这些接口引入了`@FunctionalInterface`注解，以明确表示这是一个函数式接口。

示例：

```java
@FunctionalInterface
public interface MyFunction {
    void apply();
}
```

Java 8 提供了许多常用的内置函数式接口，如`Consumer`、`Supplier`、`Function`、`Predicate`等，方便配合 Lambda 表达式使用。

### 3.**方法引用和构造器引用**

### 4.默认方法（Default Methods）

Java 8 允许在接口中定义方法的默认实现，称为**默认方法**，这样接口的升级不会强制要求所有实现类进行修改。

示例：

```java
public interface MyInterface {
    void existingMethod();

    // Java 8 新增的默认方法
    default void newMethod() {
        System.out.println("默认方法的实现");
    }
}
```

### 5.**Stream API**

Java 8 引入了强大的**Stream API**，用于处理集合和数组的数据流操作。`Stream`使得代码能够用声明式编程风格处理数据操作，如过滤、排序、映射、归约等

示例：

```java
List<String> names = Arrays.asList("Tom", "Jerry", "Alice", "Bob");

// 使用Stream进行过滤、排序和输出
names.stream()
     .filter(name -> name.startsWith("T"))
     .sorted()
     .forEach(System.out::println);
```

### 6.Optional 类

`Optional`类用于解决可能出现的`NullPointerException`问题。它可以用于明确表示某个值可能为空，从而避免大量的空值检查。

### 7.新日期和时间 API

Java 8 引入了全新的日期和时间 API，使用`java.time`包，解决了旧的`java.util.Date`和`java.util.Calendar`类的不足。

常用类包括：

- `LocalDate`：表示不包含时间的日期
- `LocalTime`：表示一天中的时间
- `LocalDateTime`：表示日期和时间
- `ZonedDateTime`：表示包含时区的日期和时间

### 8.Stream 的并行处理

### 9.Nashorn JavaScript 引擎

### 10.Base64 编码与解码
