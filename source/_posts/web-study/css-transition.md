---
layout: _posts
title: css-过渡（transition）
date: 2024-05-20 15:43:23
category: WebStudy
tags:
  - CSS
  - 学习记录
---

### 说明

transition CSS 属性是 transition-property、transition-duration、transition-timing-function 和 transition-delay 的一个简写属性。过渡可以为一个元素在不同状态之间切换的时候定义不同的过渡效果。比如在不同的伪元素之间切换，像是 :hover，:active 或者通过 JavaScript 实现的状态变化。

> transition: < property > < duration > < timing-function > < delay >;

### 属性说明

#### transition-property

- 说明: 指定哪个或哪些 CSS 属性用于过渡。只有指定的属性才会在过渡中发生动画，其他属性仍如通常那样瞬间变化。
- transition-property: none | all | property

> none: 没有过渡动画
> all: 所有可被动画的属性都表现出过渡动画
> property: 定义应用过渡效果的 CSS 属性名称列表，列表以逗号分隔

#### transition-duration

- 说明: 指定过渡的时长。你可以为所有属性指定一个值，或者指定多个值，或者为每个属性指定不同的时长。
- transition-duration: time

> time: 规定完成过渡效果需要花费的时间，单位为秒或毫秒，默认为 0，意味着不会有效果

#### transition-timing-function 指定应用过渡属性的名称

- 说明: 指定一个函数，定义属性值怎么变化。缓动函数定义属性如何计算。大多数缓动函数由四点定义一个立方贝塞尔曲线。也可以从 Easing Functions Cheat Sheet 选择缓动效果
- transition-timing-function: ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n)

> ease: 默认值，规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）
> linear: 以常量速度进行过渡，规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。。
> ease-in: 慢速开始，规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
> ease-out: 慢速结束，规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
> ease-in-out: 先慢后快，规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
> cubic-bezier(n,n,n,n): 定义一个 cubic-bezier 函数，用来定义自己的缓动效果，可能的值是 0 至 1 之间的数值。

#### transition-delay 指定应用过渡属性的名称

- 说明: 指定延迟，即属性开始变化时与过渡开始发生时之间的时长。
- transition-delay: time

> time: 规定延迟的时间，单位为秒或毫秒，默认为 0，意味着属性在过渡之前不会延迟