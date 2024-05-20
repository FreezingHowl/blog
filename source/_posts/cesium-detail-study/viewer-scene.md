---
title: supermapCesium-视图与场景（2）
category: SupermapCesium
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

- **terrainProvider** 地形提供器，用于提供地球表面的地形数据。

- **imageryLayers** 图像图层集合，用于管理和显示地球表面的图像图层。

- **baseColor** 设置地球的基础颜色。

- **show** 控制是否显示地球球体。

- **shadows** 设置地球球体的阴影效果。

- **enableLighting** 控制是否启用光照效果。

- **showWaterEffect** 控制是否显示水面效果。

- **showGroundAtmosphere** 控制是否显示大气层效果。

- **showSkyAtmosphere** 控制是否显示天空大气层。

- **showSunBloom** 控制是否显示太阳的辐射效果。

### 方法

- **globe.pick(ray, scene, result)** 根据给定的射线和场景对象，获取地球表面上的交点。

- **getHeight(cartographic)** 获取给定位置的地表高程。

- **getTerrainHeight(cartographic)** 获取给定位置的地形高程。

- **pickEllipsoid(ray, scene, result)** 获取地球椭球体上的交点。

### 示例代码

``` javascript

// 创建一个 Cesium 场景
const viewer = new Cesium.Viewer('cesiumContainer');

// 获取 globe 对象的引用
const globe = viewer.scene.globe;

// 设置地形提供器
globe.terrainProvider = new Cesium.CesiumTerrainProvider({
    url: Cesium.IonResource.fromAssetId(1), // 使用 Cesium Ion 提供的地形数据
});

// 添加图像图层
globe.imageryLayers.addImageryProvider(new Cesium.SingleTileImageryProvider({
    url: 'path/to/your/image.png', // 图像路径
    rectangle: Cesium.Rectangle.fromDegrees(-120, 20, -100, 30) // 图像显示的范围
}));

// 设置地球的基础颜色
globe.baseColor = new Cesium.Color(0.5, 0.5, 0.5, 1.0);

// 控制是否显示地球球体
globe.show = false;

// 启用地球的阴影效果
globe.shadows = true;

// 启用光照效果
globe.enableLighting = true;

// 根据射线获取地球表面上的交点
const ray = viewer.camera.getPickRay(new Cesium.Cartesian2(0.5, 0.5));
const result = new Cesium.Cartesian3();
const pickedPosition = globe.pick(ray, viewer.scene, result);
if (Cesium.defined(pickedPosition)) {
    console.log('Picked position:', pickedPosition);
}

```

## Camera 介绍

### 属性
- **position** 获取或设置相机的位置。
- **direction** 获取或设置相机的方向。
- **up** 获取或设置相机的上方向。
- **right** 获取或设置相机的右方向。
- **heading** 获取或设置相机的方位角。
- **pitch** 获取或设置相机的俯仰角。
- **roll** 获取或设置相机的翻滚角。
- **frustum** 获取相机的视锥体。
- **focalLength** 获取或设置相机的焦距。
- **frustumCulling** 相机视锥体剔除。
- **near** 获取或设置相机的近裁剪面距离。
- **far** 获取或设置相机的远裁剪面距离。
- **frustumPlanes** 获取相机的视锥体平面。
- **constrainedAxis** 获取或设置相机的限制轴。

### 方法
- **getPickRay(windowPosition, result)** 根据窗口位置获取相机射线。
- **lookAt(target, offset)** 使相机观察指定的目标点，并可以设置相机的偏移量。
- **flyTo(options)** 使相机飞行到指定的目标点，并可以设置飞行的参数。
- **setView(options)** 设置相机的视图参数，包括位置、方向、上方向等。
- **otateAroundAxis(axis, angle)** 绕指定轴旋转相机。

### 示例代码
``` javascript
// 创建一个 Cesium 场景
const viewer = new Cesium.Viewer('cesiumContainer');

// 获取 camera 对象的引用
const camera = viewer.camera;

// 设置相机的位置
camera.position = new Cesium.Cartesian3(1000000.0, 0.0, 1000000.0);

// 获取相机的方向
const direction = camera.direction;

// 获取相机的上方向
const up = camera.up;

// 获取相机的视锥体
const frustum = camera.frustum;

// 设置相机的方位角和俯仰角
camera.setView({
    destination: Cesium.Cartesian3.fromDegrees(-75.0, 45.0, 500000.0),
    orientation: {
        heading: Cesium.Math.toRadians(90.0),
        pitch: Cesium.Math.toRadians(-45.0),
        roll: 0.0
    }
});

// 飞行到指定位置
camera.flyTo({
    destination: Cesium.Cartesian3.fromDegrees(-75.0, 45.0, 500000.0),
    orientation: {
        heading: Cesium.Math.toRadians(90.0),
        pitch: Cesium.Math.toRadians(-45.0),
        roll: 0.0
    },
    duration: 3.0
});

// 控制相机的缩放
camera.zoomIn(1000.0);

// 绕指定轴旋转相机
camera.rotateAroundAxis(Cesium.Cartesian3.UNIT_Z, Cesium.Math.toRadians(45.0));

```
