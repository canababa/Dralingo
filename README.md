<div align="center">
<img src="head-cover.png" alt="icon"/>

# 龙译-Dralingo

专为安卓手机和游戏掌机玩家开发的翻译软件，由萌译MoeTranslator基础上，二次开发而来，特此感谢萌译大佬开源。

完全免费，无广告，为爱发电！ 如果深得你心，请我喝杯咖啡吧。[～咖啡～咖啡](https://raw.githubusercontent.com/canababa/Dralingo/refs/heads/main/pay.png)


</div>


## 使用介绍请查看B站：

## 简介 

龙译是一款安卓端的翻译软件，基于无障碍截图权限开发。所以只适合安卓的掌机使用，Linux掌机不能使用。

正好掌机按键映射也需要无障碍权限，所以没用市面上主流的MediaProjection方案，更加省电和减少cpu性能开销。

-特色功能：

1.双选区翻译，第二选区可自定义，可同时自动翻译

2.术语库匹配（自定义属性后缀、双语双向匹配）

3.自动翻译（帧差检测、文本缓存匹配、智能省电）

4.全屏智能覆盖翻译（智能采样、多行合并）

5.手柄按键映射，自定义手柄按键绑定特定功能

6.历史记录功能

<img src="display.png"/>

## 一、翻译功能

翻译是龙译的核心功能，支持不同的API（包括AI接口或常见的机器翻译接口），每个API的申请方法可去萌译官网中查看[详细的教程](https://www.moetranslate.top/docs/translation/apiconfig/)。

除此之外，您还可以**自定义API接口**来进行翻译，上述两种模式均支持自定义API接口，也就是说，**您可以在局域网内的电脑上搭建您喜欢的翻译服务（如：搭建Sakura本地翻译模型），然后通过萌译在手机上享受这些服务带来的便利**。这种方法需要您掌握一定的编程知识和计算机网络知识，在萌译官网上有一些简易的[搭建教程](https://www.moetranslate.top/docs/translationapi/customtext/)。

### 1、使用方法

简易的使用方法：

1.先开启无障碍权限、通知权限、悬浮窗权限

2.选择API接口

3.选择翻译模式：区域翻译、全屏翻译

4.点击开始翻译后，点击悬浮球翻译

5.可在个性化设置页面中自定义设置

<img src="menu.png"/>

<img src="use.png"/>

### 2、预置API介绍

<img src="API.png"/>

## 二、其他功能

### 1、术语库匹配功能

<img src="glossary.png"/>
<img src="translator.png"/>


### 2、手柄按键映射
<img src="mapping.png"/>

### 3、历史记录工能




## 捐助项目

如果您想给开发者物质上的帮助，那就请我喝杯咖啡吧。

<img src="pay2.png"/>

## 使用到的其他开源项目

- [RTranslator](https://github.com/niedev/RTranslator)  
  本地运行的适用于 Android 的开源实时翻译应用程序。萌译中的NLLB翻译功能使用了 RTranslator 项目的模型和代码。

- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)  
  全球领先的 OCR 工具包与文档 AI 引擎。萌译中的OCR步骤使用了 PaddlePaddle/PP-OCRv6_small_rec_onnx 的模型。

- [Live 2D SDK](https://www.live2d.com/)  
  用于展示和操作 Live2D 模型的框架。萌译的 Live 2D 功能使用到了 Live 2D SDK。

- [ColorPicker](https://github.com/jaredrummler/ColorPicker)  
  Android 的颜色选择器组件。

- [Konfetti](https://github.com/DanielMartinus/Konfetti)  
  Android 的粒子效果库，用于创建炫酷的视觉效果。

更多使用到的基础开源项目请在萌译中的【设置】->【关于】->【开放源代码声明】中查看。
