﻿---
title: 设计模式之六大设计原则
comments: true
date: 2016-03-17 13:20:53
update: 2016-03-17 13:20:53
categories: 设计模式
tags: ['设计模式','设计原则','Java']
---

很久之前就听说过设计模式的大名，但是一直没有集中精力完整的去学习设计模式，最近打算完整的学习一下设计模式，并把学习的收获及心得记录下来。本篇博客主要内容为：设计模式的六大设计原则。

<!-- more -->

![Design-Pattem-MindMap](http://7xrnl9.com1.z0.glb.clouddn.com/image%2F%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%2FDesign-Pattem-MindMap.png)

## 一、概述

设计模式（Design pattern）是一套被反复使用、多数人知晓的、经过分类编目的、代码设计经验的总结。使用设计模式是为了可重用代码、让代码更容易被他人理解、保证代码可靠性。 毫无疑问，设计模式于己于他人于系统都是多赢的；设计模式使代码编制真正工程化；设计模式是软件工程的基石脉络，如同大厦的结构一样。

而**设计原则**则是设计模式所遵循的规则，设计模式就是实现了这些原则，从而达到了代码复用、增加可维护性的目的。

## 二、六大设计原则

### 2.1 单一职责原则(Single Responsibility Principle - SRP)

一个类，只有一个引起它变化的原因。应该只有一个职责。每一个职责都是变化的一个轴线，如果一个类有一个以上的职责，这些职责就耦合在了一起。这会导致脆弱的设计。当一个职责发生变化时，可能会影响其它的职责。另外，多个职责耦合在一起，会影响复用性。例如：要实现逻辑和界面的分离。

### 2.2 开放封闭原则(Open Closed Principle - OCP)

软件实体应该是可扩展，而不可修改的。也就是说，**对扩展是开放的，而对修改是封闭的**。
**对扩展开放**，意味着有新的需求或变化时，可以对现有代码进行扩展，以适应新的情况。
**对修改封闭**，意味着类一旦设计完成，就可以独立完成其工作，而不要对类进行任何修改。
封装变化，是实现开放封闭原则的重要手段，对于经常发生变化的状态一般将其封装为一个抽象。
拒绝滥用抽象，只将经常变化的部分进行抽象，这种经验可以从设计模式的学习与应用中获得。

### 2.3 里氏替换原则(Liskov Substitution Principle - LSP)

里氏替换原则通俗的来讲就是：**子类可以扩展父类的功能，但不能改变父类原有的功能**。它包含以下4层含义：
> 1. 子类可以实现父类的抽象方法，但不能覆盖父类的非抽象方法。
> 2. 子类中可以增加自己特有的方法。
> 3. 当子类的方法重载父类的方法时，方法的前置条件（即方法的形参）要比父类方法的输入参数更宽松。
> 4. 当子类的方法实现父类的抽象方法时，方法的后置条件（即方法的返回值）要比父类更严格。

### 2.4 最少知识原则(Least Knowledge Principle - LKP)

最少知识原则又叫**迪米特法则**。核心思想是：**低耦合、高内聚**
一个实体应当尽量少的与其他实体之间发生相互作用，使得系统功能模块相对独立。也就是说一个软件实体应当尽可能少的与其他实体发生相互作用。这样，当一个模块修改时，就会尽量少的影响其他的模块，扩展会相对容易，这是对软件实体之间通信的限制，它要求限制软件实体之间通信的宽度和深度。

### 2.5 接口隔离原则(Interface Segregation Principle - ISP)

接口隔离原则的含义是：**建立单一接口，不要建立庞大臃肿的接口，尽量细化接口，接口中的方法尽量少**。
采用接口隔离原则对接口进行约束时，要注意以下几点：

> 1. 接口尽量小，但是要有限度。对接口进行细化可以提高程序设计灵活性是不挣的事实，但是如果过小，则会造成接口数量过多，使设计复杂化。所以一定要适度。
> 2. 为依赖接口的类定制服务，只暴露给调用的类它需要的方法，它不需要的方法则隐藏起来。只有专注地为一个模块提供定制服务，才能建立最小的依赖关系。
> 3. 提高内聚，减少对外交互。使接口用最少的方法去完成最多的事情。

### 2.6 依赖倒置原则(Dependence Inversion Principle - DIP)

依赖倒置原则的核心思想是**面向接口编程**，不应该面向实现类编程。
在实际编程中，要做到下面3点：

> 1. 低层模块尽量都要有抽象类或接口，或者两者都有。
> 2. 变量的声明类型尽量是抽象类或接口。
> 3. 使用继承时遵循里氏替换原则。

## 三、其他设计原则

除了以上六大设计原则之外。还有一些其他的设计原则，下面只做简单介绍，

### 3.1 组合/聚合复用原则（Composition/Aggregation Reuse Principle - CARP）

当要扩展类的功能时，优先考虑使用组合，而不是继承。这条原则在 23 种经典设计模式中频繁使用，如：代理模式、装饰模式、适配器模式等。可见江湖地位非常之高！
这也是面向对象中的一个**重要原则**。

### 3.2 无环依赖原则（Acyclic Dependencies Principle - ADP）

当 A 模块依赖于 B 模块，B 模块依赖于 C 模块，C 依赖于 A 模块，此时将出现循环依赖。在设计中应该避免这个问题，可通过引入“中介者模式”解决该问题。

### 3.3 共同封装原则（Common Closure Principle - CCP）

应该将易变的类放在同一个包里，将变化隔离出来。该原则是“开放-封闭原则”的延生。

### 3.4 共同重用原则（Common Reuse Principle - CRP）

如果重用了包中的一个类，那么也就相当于重用了包中的所有类，我们要尽可能减小包的大小。

### 3.5 好莱坞原则（Hollywood Principle - HP）

好莱坞明星的经纪人一般都很忙，他们不想被打扰，往往会说：Don't call me, I'll call you. 翻译为：不要联系我，我会联系你。对应于软件设计而言，最著名的就是“控制反转”（或称为“依赖注入”），我们不需要在代码中主动的创建对象，而是由容器帮我们来创建并管理这些对象。

### 3.6 不要重复你自己（Don't repeat yourself - DRY）

不要让重复的代码到处都是，要让它们足够的重用，所以要尽可能地封装。

### 3.7 保持它简单与傻瓜（Keep it simple and stupid - KISS）

不要让系统变得复杂，界面简洁，功能实用，操作方便，要让它足够的简单，足够的傻瓜。

### 3.8 高内聚与低耦合（High Cohesion and Low Coupling - HCLC）

模块内部需要做到内聚度高，模块之间需要做到耦合度低。

### 3.9 惯例优于配置（Convention over Configuration - COC）

尽量让惯例来减少配置，这样才能提高开发效率，尽量做到“零配置”。很多开发框架都是这样做的。

### 3.10 命令查询分离（Command Query Separation - CQS）

在定义接口时，要做到哪些是命令，哪些是查询，要将它们分离，而不要揉到一起。

### 3.11 关注点分离（Separation of Concerns - SOC）

将一个复杂的问题分离为多个简单的问题，然后逐个解决这些简单的问题，那么这个复杂的问题就解决了。难就难在如何进行分离。

### 3.12 契约式设计（Design by Contract - DBC）

模块或系统之间的交互，都是基于契约（接口或抽象）的，而不要依赖于具体实现。该原则建议我们要面向契约编程。

### 3.13 你不需要它（You aren't gonna need it - YAGNI）

不要一开始就把系统设计得非常复杂，不要陷入“过度设计”的深渊。应该让系统足够的简单，而却又不失扩展性，这是其中的难点。