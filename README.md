<div align="center">
<img src="head-cover.png" alt="icon"/>

# 龙译-Dralingo

专业游戏掌机玩家开发的翻译软件，由萌译MoeTranslator基础上，二次开发莱尔，特此感谢萌译大佬开源。

</div>

## 简介

萌译是一款安卓端的翻译软件，基于Android 11+的无障碍截图权限开发。

-特色功能：

1.双选区翻译，第二选区可自定义，可同时自动翻译

2.术语库匹配（自定义属性后缀、双语双向匹配）

3.自动翻译（帧差检测、文本缓存匹配、智能省电）

4.全屏智能覆盖翻译（智能采样、多行合并）

<img src="display.png"/>

支持两种模式：

- **本地OCR识别+文本翻译：** 通过PaddleOCR或ML Kit实现**本地**OCR识别（支持的源语言有中文、日文、英文、韩文、法语、德语、西班牙语等拉丁语系），然后将识别到的文字使用特定API进行翻译，获取翻译结果。
  
- **直接上传图片进行翻译：** 将截图直接上传给特定API，获取翻译结果，适用于源语言在OCR识别列表外的情况。

## 一、翻译功能

翻译是萌译的核心功能，对于上述两种模式，分别支持不同的API（包括AI接口或常见的机器翻译接口），每个API的申请方法在萌译官网中都有[详细的教程](https://www.moetranslate.top/docs/translation/apiconfig/)。

除此之外，您还可以**自定义API接口**来进行翻译，上述两种模式均支持自定义API接口，也就是说，**您可以在局域网内的电脑上搭建您喜欢的翻译服务（如：搭建Sakura本地翻译模型），然后通过萌译在手机上享受这些服务带来的便利**。这种方法需要您掌握一定的编程知识和计算机网络知识，在萌译官网上有一些简易的[搭建教程](https://www.moetranslate.top/docs/translationapi/customtext/)。

### 1、使用方法

简易的使用方法介绍如下图所示，更详细的使用方法在您初次使用App时会有详细的介绍，您也可[点击此处](https://www.moetranslate.top/docs/usetranslation/)去官网查看更详细的使用方法。

<img src="markdown/images/menu.png"/>

<img src="markdown/images/use.png"/>

### 2、预置API介绍

<img src="markdown/images/API.png"/>

- **本地OCR识别+文本翻译：** 这是比较推荐的一种翻译方式，预置支持的API有：

> **ML Kit翻译：** 属于本地AI翻译。除了第一次使用需下载模型（约100MB）外，其余时间可离线使用。搭配本地OCR识别，可实现全程离线翻译。值得注意的是，由于该模型体积很小，因此翻译质量较低，适合特殊情况下使用。  
> [启用教程](https://www.moetranslate.top/docs/translationapi/mlkit/)  
> 翻译质量：★（1星）

> **NLLB翻译：** 属于本地AI翻译。除了第一次使用需下载模型（约1GB）外，其余时间可离线使用。搭配本地OCR识别，可实现全程离线翻译。该模型相较于前者，翻译质量有所提升，支持的目标语言也更多，但受限于手机端算力，翻译质量相较于在线API差距仍然很大。  
> [启用教程](https://www.moetranslate.top/docs/translationapi/nllb/)  
> 翻译质量：★★（2星）

> **LlamaCpp引擎：** 属于本地AI翻译。**可任意导入LlamaCpp引擎支持的模型（GGUF格式）**，导入后可离线使用。搭配本地OCR识别，可实现全程离线翻译。翻译质量取决于选择的模型。  
> [启用教程](https://www.moetranslate.top/docs/translationapi/llamacpp/)  
> 翻译质量：★★★★（4星）

> **必应翻译：** 属于在线翻译API。这是唯一一个不需要提前配置API Key即可使用的在线翻译方式。其实现原理是通过模拟浏览器访问网页的行为来实现翻译，依赖于网页结构和token提取，这是非常不规范的行为，稳定性较差。也正因为如此，萌译无法保证它随时可用。该方法翻译质量尚可，不过由于它实现方式的特殊性，还是适合特殊情况下使用。  
> [启用教程](https://www.moetranslate.top/docs/translationapi/bing/)  
> 翻译质量：★★★★（4星）

> **小牛翻译：** 属于在线翻译API。需要提前配置API Key方可使用。注册后即可享受**每天20万字符的免费调用额度**，一般用户足够使用。API申请方法也非常简单，翻译质量很高，综合考虑的不二之选。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/niutrans/)  
> 翻译质量：★★★★★（5星）

> **聚合 AI 翻译：** 属于在线翻译API。需要提前配置API Key方可使用。萌译支持兼容OpenAI接口规范的AI接口，因此可以使用ChatGPT、Qwen、DeepSeek等模型进行翻译。这里比较推荐使用Qwen，**目前Qwen的各个模型都赠送大量的免费Token**，翻译质量很高。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/uniaitrans/)  
> 翻译质量：★★★★★（5星）

> **火山引擎：** 属于在线翻译API。需要提前配置API Key方可使用。这是字节跳动旗下的翻译API，注册后即可享受**每月200万字符的免费调用额度**，一般用户足够使用。API申请方法相比小牛翻译要复杂一些，翻译质量较高。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/volc/)  
> 翻译质量：★★★★✬（4.5星）

> **Azure AI 翻译：** 属于在线翻译API。需要提前配置API Key方可使用。这是微软旗下的翻译API，实际上就是必应翻译的API版，注册后即可享受**每月200万字符的免费调用额度**，一般用户足够使用。API申请方法比较复杂，翻译质量尚可。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/azure/)  
> 翻译质量：★★★★（4星）

> **DeepL 翻译：** 属于在线翻译API。需要提前配置API Key方可使用。这是DeepL的翻译API，注册后即可享受**每月50万字符的免费调用额度**，一般用户足够使用。API申请方法比较复杂，需要国外信用卡，翻译质量较好。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/deepl/)  
> 翻译质量：★★★★（4星）

> **百度翻译：** 属于在线翻译API。需要提前配置API Key方可使用。注册后即可享受**每月100万字符的免费调用额度**，一般用户足够使用。API申请方法比较简单，翻译质量一般。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/baidu/)  
> 翻译质量：★★★✬（3.5星）

> **腾讯云：** 属于在线翻译API。需要提前配置API Key方可使用。注册后即可享受**每月500万字符的免费调用额度**，免费额度很大。API申请方法稍微复杂一些，翻译质量很一般。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/tencent/)  
> 翻译质量：★★★（3星）

- **直接上传图片进行翻译：** 直接把截图上传给设定的API来翻译，预置支持的API有：

> **百度翻译：** 属于在线翻译API。需要提前配置API Key方可使用。注册后即可享受**每月1万次的图片翻译免费调用次数**，一般用户足够使用。API申请方法比较简单，和上面的文字翻译相比，带来的质量提升主要在OCR的精准度上。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/baidu/)  
> 翻译质量：★★★★（4星）

> **腾讯云：** 属于在线翻译API。需要提前配置API Key方可使用。注册后即可享受**每月1万次的图片翻译免费调用次数**，一般用户足够使用。API申请方法稍微复杂一些，由于腾讯云的图片翻译仅支持单行翻译，因此当一句话多于一行时，会造成翻译严重不正确的情况。  
> [申请教程](https://www.moetranslate.top/docs/translationapi/tencent/)  
> 翻译质量：★★（2星）

## 二、其他功能

### 1、Live 2D模型查看

<img src="markdown/images/l2d.png"/>

得益于[Live 2D的SDK](https://www.live2d.com/sdk/about/)，萌译支持导入Live 2D模型，并自动解析模型附带的动作和表情，然后用户可选择特定的动作和表情播放，实现随时随地欣赏Live 2D角色。

具体的导入教程和注意事项可[点击此处](https://www.moetranslate.top/docs/live2d/importmodel/)查看。

\*图中的鹿目圆模型来自魔法纪录，在此仅作为预置模型展示软件功能，版权归原作者所有。

### 2、Gemini AI聊天

<img src="markdown/images/gemini.png"/>

Google的Gemini正处于全民公测阶段，而且实际上Gemini模型的实力不俗，刚好其[Gemini模型](https://ai.google.dev/gemini-api/docs/pricing)的API有免费方案可以使用，因此我们可获取API后在萌译中和其进行聊天。值得注意的是中国大陆用户需开启VPN后使用。

具体的使用教程可[点击此处](https://www.moetranslate.top/docs/gemini/apiapplication/)查看。

## 捐助项目

如果您想给开发者物质上的帮助，可以[点击此处](https://www.moetranslate.top/support/)来捐赠。

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
