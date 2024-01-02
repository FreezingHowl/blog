---
title: supermapCesium-视图与场景（2）
category: supermapCesium
tags:
  - 学习思考
  - 学习记录
abbrlink: 8b95755c
date: 2023-12-07 19:52:31
---

<!--more-->

## Globe介绍

Scene 对象下的 globe 属性是用来配置和管理地球（或其他行星体）的属性的。

### 属性

- **ellipsoid** 表示地球的椭球体（Ellipsoid）参数，包括半长轴、半短轴等参数，定义了地球的形状。

``` javascript

const scene = viewer.scene

// 获取椭球体参数
const ellipsoid = scene.globe.ellipsoid

```

- **baseColor** 表示地球表面的基本颜色。可以用于改变地球整体的颜色。

``` javascript

const scene = viewer.scene

// 移除默认底图
viewer.imageryLayers.removeAll()

// 修改球体颜色
scene.globe.baseColor = Cesium.Color.fromCssColorString('#ec0000') 

```

- **shadows** 表示地球表面阴影的模式，用于配置光照效果。

``` javascript

const scene = viewer.scene

// 关闭阴影
scene.globe.shadows = Cesium.ShadowMode.ENABLED

```

- **imageryLayers** 表示地球表面的 ImageryLayer 集合，用于管理地球表面的图像图层。

``` javascript

const scene = viewer.scene

// 获取图像图层
const imageryLayers = scene.globe.imageryLayers;

```

- **fog** 表示地球表面的雾效配置，影响地球表面的可见性和颜色。

``` javascript

const scene = viewer.scene

// 禁用雾气效果
scene.globe.fog.enabled = false;

```

- **fog** 表示地球表面的雾效配置，影响地球表面的可见性和颜色。

``` javascript

const scene = viewer.scene

// 禁用雾气效果
scene.globe.fog.enabled = false;

```

### 方法

- **globe.pick(ray, scene, result)** 用于在地球表面上进行拾取操作，获取射线与地球表面的交点。

``` javascript

// 获取场景的 globe 对象
const globe = viewer.scene.globe;

// 创建一个射线，从相机发射
const ray = viewer.camera.getPickRay(new Cesium.Cartesian2(0.5, 0.5));

// 创建一个用于存储拾取结果的 Cartesian3 对象
const result = new Cesium.Cartesian3();

// 进行拾取操作
const pickedPoint = globe.pick(ray, viewer.scene, result);

// 检查拾取结果
if (Cesium.defined(pickedPoint)) {
    console.log('拾取到地球表面上的点坐标:', pickedPoint);
} else {
    console.log('射线没有与地球表面相交');
}

```

