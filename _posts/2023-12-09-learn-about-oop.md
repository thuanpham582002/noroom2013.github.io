---
layout: post
title: Learn about OOP
subtitle: Simple things about OOP
tags: [ oop ]
comments: true
author: NoRoom2013
---

## Table of Contents

- [What is OOP?](#what-is-oop)
- [Elements of OOP](#elements-of-oop)
- [4 Pillars of OOP](#4-pillars-of-oop)]
- [Encapsulation](#encapsulation)
- [Abstraction](#abstraction)
- [Inheritance](#inheritance)
- [Polymorphism](#polymorphism)
- [Difference between Abstract Class and Interface](#difference-between-abstract-class-and-interface)

## What is OOP?

Lập trình hướng đối tượng là một trong những kỹ thuật lập trình phổ biến nhất hiện nay.
Nó cho phép lập trình viên tạo ra các đối tượng trong code, mô phỏng các đối tượng trong thế giới thực.
Mỗi đối tượng có thể chứa dữ liệu và các hành vi riêng.
Mỗi đối tượng có thể tương tác với nhau thông qua các hành vi của chúng.

## Elements of OOP

- Class : Lớp - là một bản thiết kế của một đối tượng.
- Object: Đối tượng - là một thể hiện của một lớp.
- Method : Phương thức - là một hành vi của một đối tượng.
- Property : Thuộc tính

## 4 Pillars of OOP

OOP có 4 nguyên tắc cơ bản là:

- Encapsulation
- Abstraction
- Inheritance
- Polymorphism

## Encapsulation

Tính đóng gói: là một cách để bảo vệ dữ liệu của một đối tượng, ngăn ngừa việc truy cập trực tiếp từ bên ngoài.
Để thực hiện tính đóng gói, ta sử dụng các phương thức getter và setter để truy cập dữ liệu của đối tượng.

```java
public class Person {
    private String name;
    private int age;
    private String address;

    public Person(String name, int age, String address) {
        this.name = name;
        this.age = age;
        this.address = address;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public String getAddress() {
        return address;
    }

    public void setName(String name) {
        this.name = name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

Khi ta muốn truy cập dữ liệu của đối tượng Person, ta sử dụng các phương thức getter và setter.
Như vậy, ta có thể phân biệt được rõ cách thức truy cập dữ liệu của đối tượng Person.

## Abstraction

Tính trừu tượng: là một cách để ẩn đi các chi tiết cài đặt của một đối tượng, chỉ hiển thị các thông tin cần thiết cho
người dùng.

```java
public abstract class Animal {
    public abstract void eat();

    public abstract void sleep();
}
```

```java
public class Dog extends Animal {
    public void bark() {
        System.out.println("Dog is barking");
    }

    @Override
    public void eat() {
        System.out.println("Dog is eating");
    }

    @Override
    public void sleep() {
        System.out.println("Dog is sleeping");
    }
}
```

```java
public class Cat extends Animal {
    public void meow() {
        System.out.println("Cat is meowing");
    }

    @Override
    public void eat() {
        System.out.println("Cat is eating");
    }

    @Override
    public void sleep() {
        System.out.println("Cat is sleeping");
    }
}
```

```java

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();

        dog.eat();
        dog.sleep();

        cat.eat();
        cat.sleep();
    }
}
```

Trong ví dụ trên, ta có một lớp trừu tượng Animal, và hai lớp Dog và Cat kế thừa từ lớp Animal.
Lớp Animal có hai phương thức trừu tượng eat() và sleep(), hai lớp Dog và Cat phải override lại hai phương thức này.
Dog và Cat có thêm hai phương thức bark() và meow(). Tuy nhiên, khi ta khởi tạo đối tượng Dog và Cat dưới dạng đối tượng
Animal
, ta chỉ có thể gọi hai phương thức eat() và sleep() của lớp Animal. (Đây là tính đa hình)
Như vậy, ta có thể hiểu rằng, lớp Animal là một lớp trừu tượng, nó chỉ hiển thị các thông tin cần thiết cho người dùng.

Hoặc 1 ví dụ khác:

```java
public class Person {
    private String name;
    private int age;
    private String address;
    private String bmi;

    private String calculateBMI() {
        // calculate bmi
        return bmi;
    }

    public Person(String name, int age, String address) {
        this.name = name;
        this.age = age;
        this.address = address;
    }

    public String getBMI() {
        return calculateBMI();
    }
}
```

Trong ví dụ trên, ta có một lớp Person, lớp này có một phương thức tính chỉ số BMI, nhưng phương thức này không được
hiển thị ra bên ngoài.
Ta chỉ có thể gọi phương thức getBMI() để lấy chỉ số BMI của đối tượng Person. Điều này giúp ta ẩn đi các chi tiết cài
đặt của phương thức tính chỉ số BMI.

## Inheritance

**Tính kế thừa**: là một cách để tái sử dụng lại các thuộc tính và phương thức của một lớp khác.
Khi một lớp kế thừa từ một lớp khác, lớp con sẽ có tất cả các thuộc tính và phương thức của lớp cha.
Lớp con có thể thêm các thuộc tính và phương thức mới, hoặc override lại các phương thức của lớp cha.

```java
public class Animal {
    private String name;
    private int age;
    private String address;

    public Animal(String name, int age, String address) {
        this.name = name;
        this.age = age;
        this.address = address;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public String getAddress() {
        return address;
    }

    public void setName(String name) {
        this.name = name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

```java
public class Dog extends Animal {
    public void bark() {
        System.out.println("Dog is barking");
    }
}
```

```java
public class Cat extends Animal {
    public void meow() {
        System.out.println("Cat is meowing");
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();

        dog.setName("Dog");
        dog.setAge(5);
        dog.setAddress("Vietnam");

        cat.setName("Cat");
        cat.setAge(3);
        cat.setAddress("Vietnam");

        System.out.println(dog.getName());
        System.out.println(dog.getAge());
        System.out.println(dog.getAddress());

        System.out.println(cat.getName());
        System.out.println(cat.getAge());
        System.out.println(cat.getAddress());
    }
}
```

``` {output}
Dog
5
Vietnam
Cat
3
Vietnam
```

## Polymorphism

**Tính đa hình**: là một cách để một đối tượng có thể thể hiện ra nhiều hình dạng khác nhau hoặc
một phương thức có thể có nhiều hình thức khác nhau.

**Các khái niệm liên quan**: Overloading, Overriding, Upcasting, Downcasting.

Đa hình có thể được thực hiện thông qua kế thừa, hoặc thông qua các interface.

2 loại đa hình:

- Đa hình tĩnh (Static polymorphism): được thực hiện thông qua overloading.
- Đa hình động (Dynamic polymorphism): được thực hiện thông qua overriding.

## Difference between Abstract Class and Interface

An **interface** is a contract between a class and the outside world.
When a class implements an interface, it promises to provide the behavior published by that interface.
It has nothing to do with inheritance; it merely says, "hey, I promise to provide these methods, variables, and/or
events." It's up to the class to fulfill that promise.

An **abstract class** is a class which cannot be instantiated.
It's more of a template from which other classes can be derived.

**Abstract classes** can have constants, members, method stubs (methods without a body) and defined methods, whereas
interfaces can only have constants and methods stubs.