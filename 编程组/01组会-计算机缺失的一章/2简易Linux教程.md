---
title: 逃不开的一节-Linux
description: 
published: true
date: 2023-11-01T14:39:59.207Z
tags: 
editor: markdown
dateCreated: 2023-11-01T14:14:44.180Z
---

# Linux
[Source Code](https://www.kernel.org/)
linux是一个开源的，维护积极的，操作系统内核，提供了丰富的系统功能，广泛的硬件兼容，和生产级别的稳定性。
## Shell
shell是一套基于文本的与操作系统交互的逻辑。
对于初次接触shell的人而言，最大的困惑就是，这个东西它能干啥？它怎么做？与UI界面相比较，shell上空荡荡的啥都没有。我们必须凭借记忆和经验来判断下一步该怎么做。
- 专注核心功能
	- 但是对于开发者来说，大量现代的工具是没有gui界面的，例如gcc工具链，openocd工具链。他们都专注与核心功能本身，并没有对用户设计ui界面，操作shell终究是每个开发者无法避免的。
- 一套贯通的逻辑
	- shell下工具的使用逻辑是高度统一的，如果你熟练使用gcc，那你可以很快学会clang，rustc等其他编译器的使用。
- IDE封装的太多内容，使得你无法真正的理解编程。
---
- shell的核心功能就是执行程序。
```shell
echo "Hello World"
```
- 常用的指令
	- ls 
  - cd 
  - touch
  - rm
  - mkdir
  - echo
  - cat
  - nano
  - vim
  - wget
  - curl
  
- 你可以给命令附加参数
```shell
ls
ls -a
ls -l
```

#### 管道
你可以重定向标准输出到文件
``` shell
echo "Hello World" >> log.txt
```