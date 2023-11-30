---
layout: _posts
title: css-动画
date: 2023-05-30 11:06:54
category: WebGis
tags:
  - CSS
  - 学习记录
---

> 浏览器最低版本支持： Chrome（43.0）、Firefox（16.0）、Opera（30.0）、Internet（10.0）
### 基础概念
#### animation属性系列
  - ```animation: name duration timing-function delay iteration-count direction```
  - ***animation-name***：
    **描述**：规定 @keyframes 动画的名称
    **语法**：``` animation-name: keyframename|none; ```
    **属性**：
      <table>
      <tbody><tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td><i>keyframename</i></td>
      <td>规定需要绑定到选择器的 keyframe 的名称。</td>
      </tr>

      <tr>
      <td>none</td>
      <td>规定无动画效果（可用于覆盖来自级联的动画）。</td>
      </tr>
      </tbody></table>

  - ***animation-duration***：
    **描述**：规定完成动画所花费的时间，以秒或毫秒计。
    **语法**：``` animation-duration: time; ```
    **属性**：
      <table>
      <tbody><tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td><i>time</i></td>
      <td>规定完成动画所花费的时间。默认值是 0，意味着没有动画效果。</td>
      </tr>
      </tbody></table>

  - ***animation-timing-function***：
    **描述**：规定动画的速度曲线。
    **语法**：``` animation-timing-function: value; ```
    **属性**：
      <table>
      <tbody>
      <tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td>linear</td>
      <td>动画从头到尾的速度是相同的。</td>
      </tr>

      <tr>
      <td>ease</td>
      <td>默认。动画以低速开始，然后加快，在结束前变慢。</td>
      </tr>

      <tr>
      <td>ease-in</td>
      <td>动画以低速开始。</td>
      </tr>

      <tr>
      <td>ease-out</td>
      <td>动画以低速结束。</td>
      </tr>


      <tr>
      <td>ease-in-out</td>
      <td>动画以低速开始和结束。</td>
      </tr>

      <tr>
      <td>cubic-bezier(<i>n</i>,<i>n</i>,<i>n</i>,<i>n</i>)</td>
      <td>在 cubic-bezier 函数中自己的值。可能的值是从 0 到 1 的数值。</td>
      <td></td>
      </tr>
      </tbody></table>

  - ***animation-delay***：
    **描述**：规定在动画开始之前的延迟。
    **语法**：``` animation-delay: time; ```
    **属性**：
      <table>
      <tbody>
      <tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td><i>time</i></td>
      <td>可选。定义动画开始前等待的时间，以秒或毫秒计。默认值是 0。</td>
      </tr>
      </tbody></table>

  - ***animation-iteration-count***：
    **描述**：规定动画应该播放的次数。
    **语法**：``` animation-iteration-count: n|infinite; ```
    **属性**：
      <table>
      <tbody><tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td><i>n</i></td>
      <td>定义动画播放次数的数值。</td>
      </tr>

      <tr>
      <td>infinite</td>
      <td>规定动画应该无限次播放。</td>
      </tr>
      </tbody></table>

  - ***animation-direction***：
    **描述**：规定是否应该轮流反向播放动画。
    **语法**：``` animation-direction: normal|alternate; ```
    **属性**：
      <table>
      <tbody><tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td>normal</td>
      <td>默认值。动画应该正常播放。</td>
      </tr>

      <tr>
      <td>alternate</td>
      <td>动画应该轮流反向播放。</td>
      </tr>
      </tbody></table>

  - ***animation-fill-mode***：
    **描述**：规定动画在执行时间之外应用的值。
    **语法**：``` animation-fill-mode : none | forwards | backwards | both; ```
    **属性**：
      <table>
      <tbody><tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td>none</td>
      <td>不改变默认行为。</td>
      </tr>

      <tr>
      <td>forwards</td>
      <td>当动画完成后，保持最后一个属性值（在最后一个关键帧中定义）。</td>
      </tr>

      <tr>
      <td>backwards</td>
      <td>在 animation-delay 所指定的一段时间内，在动画显示之前，应用开始属性值（在第一个关键帧中定义）。</td>
      </tr>

      <tr>
      <td>both</td>
      <td>向前和向后填充模式都被应用。</td>
      </tr>

      </tbody></table>

  - ***animation-play-state***：
    **描述**：规定动画是正在运行还是暂停。
    **语法**：``` animation-play-state: paused|running; ```
    **属性**：
      <table>
      <tbody><tr>
      <th style="width:25%;">值</th>
      <th>描述</th>
      </tr>

      <tr>
      <td>paused</td>
      <td>规定动画已暂停。</td>
      </tr>

      <tr>
      <td>running</td>
      <td>规定动画正在播放。</td>
      </tr>
      </tbody></table>

#### @keyframes属性
  - **描述**：规定动画模式。
  - **语法**：``` @keyframes animationname {keyframes-selector {css-styles;}} ```
  - **属性**：

    <table>
    <tbody><tr>
    <th style="width:25%;">值</th>
    <th>描述</th>
    </tr>

    <tr>
    <td><i>animationname</i></td>
    <td>必需。定义动画的名称。</td>
    </tr>

    <tr>
    <td><i>keyframes-selector</i></td>
    <td>
      <p>必需。动画时长的百分比。</p>
      <p>合法的值：</p>
        0-100% 、
        from（与 0% 相同）、
        to（与 100% 相同）
    </td>
    </tr>

    <tr>
    <td><i>css-styles</i></td>
    <td>必需。一个或多个合法的 CSS 样式属性。</td>
    </tr>
    </tbody></table>
### 应用范围分析
- 基础使用：
  ```
  div {
    width: 100px;
    height: 100px;
    background-color: red;
    animation-name: example;
    animation-duration: 4s;
  }

  @keyframes example {
    0% {
      background-color: red;
    }
    25% {
      background-color: yellow;
    }
    50% {
      background-color: blue;
    }
    100% {
      background-color: green;
    }
  }
  ```