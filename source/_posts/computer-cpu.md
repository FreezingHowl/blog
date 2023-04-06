---
title: 计算机硬件-CPU（中央处理器）
category: 计算机基础知识
tags:
  - 计算机
  - 硬件
  - 知识普及
cover: "/img/top-img/top_img_1.webp"
---

### 介绍

CPU（central processing unit）即中央处理器，是计算机系统的运算和控制核心，是信息处理、程序运行的最终执行单元；

CPU 主要功能是解释计算机指令以及处理计算机软件中的数据。

CPU 由运算器、控制器和寄存器及实现它们之间联系的数据、控制及状态的总线构成。

### 性能衡量指标

- 主频： CPU 运行计算时工作频率，每秒的运算速度
  - 睿频： Intel 的加速技术，性能分配上实现按需分配，根据系统的运行自动调整频率。
  - 超频： CPU 和主板都支持超频时，可手动调整频率。
- 核心数： 计算核心数，核心数越多可以打开的程序就越多，同时进行多任务计算的能力也越高。
- 位数： CPU 位数=CPU 中寄存器的位数=CPU 能够一次并行处理的数据宽度（位数）=数据总线宽度。（pg.现在的计算机处理器一般都是 64 位)
- 缓存指令集: CPU 缓存,用于暂存指令。

### 后缀详解

#### intel 处理器含义：

- X：高端牛逼处理器
- K：解锁超频模式的处理器，适合超频玩家
- F：没有内置核显，需要搭配额外的独立显卡
- S：节能版处理器，相比于同型号不带 S 的处理器性能差一些
- T：相比于同型号后面带 S 的更加节能，但是功耗更低，适合长时间开机但是对性能要求不那么高的用户
- U：笔记本低功耗处理器，性能偏弱，续航能力强，多用于轻薄本
- Q：笔记本高性能四核处理器
- M：移动版 CPU
- Y：超低功耗处理器，性能很弱，功耗很低，大多数用于平板电脑
- H：高电压处理器，功耗高、主频高的处理器
- R：有 Iris 的核显，没有独立显卡的情况下有比较强的图形处理能力
- G：与 AMD 合作的产物，带 AMD 家的 Vega 牛逼核显

#### AMD 处理器含义：

- X：高端牛逼处理器
- K：解锁超频模式的处理器，适合超频玩家
- U：低功耗处理器，性能偏弱，续航能力强，一般用于轻薄本
- G：有 Vega 的核显，没有独立显卡的情况下有比较强的图形处理能力
- H：高电压处理器，功耗高主频高的处理器
- E：低功耗处理器，性能弱
- T：比较古老的 AMD 处理器后缀 T 表示支持 Turbo 睿频技术，如果是比较新版的，一般跟 Intel 一样表示超低功耗
- B：一般是低功耗的商务本
- C：一般用于 Chrome OS 的笔记本电脑
- W: 是指工作的专业 CPU，最适合编程画图渲染的朋友。
- WX: 这个后缀 CPU 是 AMD 平台中最好最贵的 CPU，性能也是最好的。经常用在玩游戏和高端设计上。

### 购买注意事项

1. 注意与主板规格适配
2. 处理器后缀含义与处理器生产厂商直接相关
3. 睿频参数较大影响 CPU 运算速度，建议和主频共同参考
4. 核数多但单核主频较低的 CPU 不建议购买

### 参考链接

```
https://www.leixue.com/ask/what-do-the-letters-of-the-cpu-suffix-represent?hl=2
https://www.jianshu.com/p/273551811a77
https://baike.baidu.com/item/%E4%B8%AD%E5%A4%AE%E5%A4%84%E7%90%86%E5%99%A8/284033
```