---
title: C++静态代码分析工具——tscancode
date: 2018-10-17 23:16:22
tags: tscancode
categories: 静态代码分析
---

#### 引言

静态代码分析是指无需运行被测代码，通过词法分析、语法分析、控制流、数据流分析等技术对程序代码进行扫描，找出代码隐藏的错误和缺陷，如参数不匹配，有歧义的嵌套语句，错误的递归，非法计算，可能出现的空指针引用等等。统计证明，在整个软件开发生命周期中，30%至70%的代码逻辑设计和编码缺陷是可以通过静态代码分析来发现和修复的。

在C++项目开发过程中，因为其为编译执行语言，语言规则要求较高，开发团队往往要花费大量的时间和精力发现并修改代码缺陷。所以C++静态代码分析工具能够帮助开发人员快速、有效的定位代码缺陷并及时纠正这些问题，从而极大地提高软件可靠性并节省开发成本。

**静态代码分析工具的优势：**

1. 自动执行静态代码分析，快速定位代码隐藏错误和缺陷。

2. 帮助代码设计人员更专注于分析和解决代码设计缺陷。

3. 减少在代码人工检查上花费的时间，提高软件可靠性并节省开发成本。

#### 检查规则

针对业内大量扫描工具在实际项目中扫描结果的影响比较，我们将代码质量问题分为以下几大类：

 　1. 致命类：可能导致程序宕机、无响应等影响范围极大的错误（如空指针、越界、内存泄漏、未初始化等）；
 　2.  逻辑类：可能造成程序不能达到预期逻辑结果的错误（如相同的条件分支、switch 缺少 break、除0错误、死循环等）；

  　　3. 编码规范及其他类：可能造成程序的可读性、可维护性较差的错误（如不可达代码、无效的变量声明、效率问题、安全隐患等）；

#### TSC

[TSC](https://github.com/Tencent/TscanCode) 针对互联网产品高效开发修复原则，工具定位为针对致命类和逻辑类问题，并不关注编码规范和编译错误。