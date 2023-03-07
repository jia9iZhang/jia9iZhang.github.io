```
layout: mypost
title: "TestNG文档翻译"
date: 2023-02-27
categories: "TestNG"
tags: 2023
```

## 1-介绍

[TestNG文档](https://testng.org/doc/documentation-main.html)

## 2-注释
以下是 TestNG 中可用注释及其属性的快速概述。
**@BeforeSuite**：注释的方法将在该套件中的所有测试运行之前运行。
**@AfterSuite**：注释的方法将在该套件中的所有测试运行后运行。
**@BeforeTest**：被注释的方法将在属于 <test> 标签内的类的任何测试方法运行之前运行。
**@AfterTest**：被注释的方法将在属于 <test> 标签内的类的所有测试方法都运行之后运行。
**@BeforeGroups**：此配置方法之前将运行的组列表。此方法保证在调用属于任何这些组的第一个测试方法之前不久运行。
**@AfterGroups**：此配置方法将在其后运行的组列表。此方法保证在调用属于这些组中的任何一个的最后一个测试方法后不久运行。
**@BeforeClass**：被注释的方法将在调用当前类中的第一个测试方法之前运行。
**@AfterClass**：被注解的方法将在当前类中的所有测试方法都运行完后运行。
**@BeforeMethod**：被注释的方法将在每个测试方法之前运行。
**@AfterMethod**：注解的方法将在每个测试方法之后运行。
TestNG 类的超类中注释的行为:
当放置在 TestNG 类的超类上时，上面的注释也将被尊重（继承）。例如，这对于将多个测试类的测试设置集中在一个公共超类中很有用。 在这种情况下，TestNG 保证“@Before”方法按继承顺序执行（最高超类首先执行，然后沿继承链向下执行），“@After”方法按相反顺序执行（沿继承链向上执行）。

- alwaysRun：对于 before 方法（beforeSuite、beforeTest、beforeTestClass 和 beforeTestMethod，但不是 beforeGroups）：如果设置为 true，则无论它属于什么组，都会运行此配置方法。 对于after 方法（afterSuite、afterClass、...）：如果设置为 true，即使先前调用的一个或多个方法失败或被跳过，此配置方法也会运行。
- dependsOnGroups：此方法所依赖的组列表。
- dependsOnMethods：此方法所依赖的方法列表。
- enabled：是否启用此类/方法上的方法。
- groups：该类/方法所属的组列表。
- inheritGroups：如果为 true，则此方法将属于在类级别的 @Test 注释中指定的组。
- onlyForGroups：仅适用于@BeforeMethod 和@AfterMethod。如果指定，则仅当相应的测试方法属于列出的组之一时才会调用此设置/拆卸方法。	

**@DataProvider**：将方法标记为为测试方法提供数据。带注释的方法必须返回一个 Object[][]，其中每个 Object[] 都可以分配测试方法的参数列表。想要从此 DataProvider 接收数据的 @Test 方法需要使用与此注释名称相同的 dataProvider 名称。

- name:此数据提供者的名称。如果未提供，此数据提供者的名称将自动设置为方法的名称。
- parallel：如果设置为 true，则使用此数据提供程序生成的测试将并行运行。默认值为假。

**@Factory**：将方法标记为工厂，该工厂返回将由 TestNG 作为测试类使用的对象。该方法必须返回 Object[]。

**@Listeners**:在测试类上定义侦听器。

- value:一组扩展org.testng.ITestNGListener的类。

**@Parameters**:描述如何将参数传递给 @Test 方法。

- value:用于填充此方法参数的变量列表。

**@Test**:将类或方法标记为测试的一部分。

- alwaysRun:如果设置为 true，则此测试方法将始终运行，即使它依赖于失败的方法也是如此。
- dataProvider:此测试方法的数据提供者的名称。
- dataProviderClass:查找数据提供者的类。如果未指定，数据提供者将在当前测试方法的类或其基类之一上查找。如果指定了该属性，则数据提供者方法需要在指定的类上是静态的。
- dependsOnGroups:此方法所依赖的组列表。
- dependsOnMethods:此方法所依赖的方法列表。
- description:此方法的说明。
- enabled:是否启用此类/方法上的方法。
- expectedExceptions:测试方法预期抛出的异常列表。如果没有异常或抛出不同于此列表中的异常，则此测试将被标记为失败。
- groups:该类/方法所属的组列表。
- invocationCount:此方法应被调用的次数。
- invocationTimeOut:对于所有调用计数的累积时间，此测试应花费的最大毫秒数。如果未指定 invocationCount，将忽略此属性
- priority:此测试方法的优先级。较低的优先级将首先安排。
- successPercentage:此方法的预期成功百分比
- singleThreaded:如果设置为 true，这个测试类的所有方法都保证在同一个线程中运行，即使测试当前正在使用 parallel="methods" 运行。此属性只能在类级别使用，如果在方法级别使用，它将被忽略。注意：此属性过去称为顺序（现已弃用）。
- timeOut:此测试应花费的最大毫秒数。
- threadPoolSize:此方法的线程池大小。将从 invocationCount 指定的多个线程调用该方法。注意：如果未指定 invocationCount，则忽略此属性
