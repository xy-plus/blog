---
title: rcore-report
date: 2020-08-05 16:40:28
categories:
  - report
tags:
  - author:xy_plus
---

# lab3

学习了自定义用户程序的编译和加载流程。

学习了操作系统的核心机制——任务切换。进程可以在运行的过程中主动或被动的暂停，然后内核将 CPU 资源交给其他进程。

学习了进程切换过程需要经历的上下文保存与恢复。

学习了通过设置 RISCV 处理器开启时钟中断，并且实现时间片轮转算法。

熟悉了用户程序与操作系统内核通过 syscall 进行交互的流程。

# lab4

学习了虚拟地址和物理地址的区别，了解了虚拟地址的作用。

学习了地址的格式与组成。

实现了物理页的分配，并通过 rust 的垃圾回收机制实现了物理页的自动回收。

学习了内核空间的地址格式。

学习了用户程序空间的地址格式。

学习了通过页表将用户虚拟地址转换为物理地址以实现在内核中通过用户指针访问用户空间的过程。

实现了 sysmap 和 sysunmap ，熟悉了页面分配与回收的过程。

# lab5

学习了 fork、exec 等关键系统调用的实现。

学习了进程的调度机制，当进程主动调用 sys_yield 或者时间片用完后，如果通过进程调度算法选择下一个进程，并切换执行。

学习了 sys_read 的实现。

学习了当进程通过 sys_exit 退出，或因错误被内核终止时，如何保存其错误码，父进程如何通过 waitpid 获取其退出信息并回收资源。

把 sys_fork 和 sys_exec 的代码拼成了 sys_spawn ，能够直接创建新进程。

实现了 stride 调度算法。stride 调度算法的测例不是很好，最后用玄学办法才勉强过了测例，很烦。建议测例改成在调度过程中 print ，然后用 python 检查 print 内容的比例。

# lab6

学习了常规文件和目录文件的设计与实现。

学习了 Linux 对文件的抽象、通用接口。

实现了 sys_linkat、sys_unlinkat、sys_stat 。

sys_stat 的实现方案比较丑陋，本来想通过计数实现，但是因为对 Rust 语法以及对实验框架不够熟悉，所以没有做成。最后通过遍历目录来计算引用计数，效率很低。

# lab8

了解了需要在内核中使用那么多 Mutex 等 crate 的原因是为了防止线程之间的相互竞争。

学习了锁、信号量、条件变量的实现。

实现了死锁检测算法。
