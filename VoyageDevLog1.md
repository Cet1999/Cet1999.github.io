---
layout: page
title: Voyage Devlog 1 - 新手上路请多指教
genre: Devlog
permalink: /VoyageDevLog1/
---

<div id="google_translate_element"></div>

<script type="text/javascript">
function googleTranslateElementInit() {
  new google.translate.TranslateElement({pageLanguage: 'zh'}, 'google_translate_element');
}
</script>

<script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>

## 导语：这是我的第一篇Devlog


我是一个【眼高手低】的人，为此我丝毫不感到羞愧并乐于承认——【眼高】代表我拥有一定的【审美素养】，【手低】代表我清楚明白自己作为游戏创作者在【创作水平】上有很大的缺陷和进步空间。这不是一件坏事，反而刺激着我不断学习新的创作技能并不间断自己的创作，促成了我内心的良性循环。而在不得不面对【审美素养远高于创作水平】的残酷现实许多年之后，终于有幸创造出了一款能够无限接近于我的审美的作品——就算没有百分之一百达到，它也比我的上一次创作更接近了百分之一百。因此我非常想通过Devlog的形式，把作为一个独立开发者的创作过程记录下来。希望若干年后再次读到这些的时候自己已经在【审美】和【创作】这两条无尽的道路上留下了清晰可见的辙印。恰好很多参与试玩的好朋友也对我的开发过程表现出了兴趣，也免去了我【写Devlog是自言自语】的担忧。

  

## Voyage是什么

Voyage的创作契机非常简单——2020年的疫情摧毁了包括我在内的所有人的所有计划。从三月春假到现在我已经在家度过了七个月的自我隔离时间，并且还会无限期地持续下去。所以这是一个让人不得不用精神代替肉体活动的时间。肉体活动的减少给我带来了增重的惨痛代价，而精神活动的增加却让我有了这个奇怪的想法：【能不能在虚拟环境里模拟出一次有意义的出门体验呢？】。于是Voyage的初始概念就应运而生了。

Voyage是一个精神世界的出游体验，它可以根据玩家输入的经纬度带领玩家前往任意的地球角落，并且根据玩家的位置进行实时生成周围环境。所以它是一个五亿平方公里的开放世界——整个地球的表面积。同时它也是一个虚拟的共享世界——玩家可以在这个虚拟的环境里遇到其他玩家，分享景色、合影、并共同留下自己的记号。

<img src="/img/post1-8.png" alt="1" class="center" width="800"/>

<img src="/img/post1-9.png" alt="1" class="center" width="800"/>

## 四周的时间内我做了什么

这个项目从9月初立项开始已经经历了四周时间，目前开发进度：

1.地图生成部分基本完成。输入坐标之后就可以开始渲染，之后根据玩家位置进行跟进实时渲染。保证完全【开放世界】的体验。

<img src="/img/post1-2.png" alt="1" class="center" width="800"/>

<img src="/img/post1-7.png" alt="1" class="center" width="800"/>

2.玩家可以在世界里种下小草，留下的草会被服务器记录，并出现在每一个其他玩家的世界里。

<img src="/img/post1-3.png" alt="1" class="center" width="800"/>

3.Postprocessing 空旷黑白的世界会在玩家走过并且种草之后重新焕发生机，加入更多色彩。

<img src="/img/post1-4.png" alt="1" class="center" width="800"/>

<img src="/img/post1-5.png" alt="1" class="center" width="800"/>

<img src="/img/post1-6.png" alt="1" class="center" width="800"/>

<img src="/img/post1-7.png" alt="1" class="center" width="800"/>

4.FPS基本功能 步行模拟器之前也做过不少，这部分算是轻车熟路了。

5.拍照功能，照片会以截图的形式保存。

6.简单的Shader和Material。

  
## 除去【享受单人开发】这个最重要的一点之外的一点经验分享：

#### Google Map API

我不是一个好的美术，要做出【地球OL】级别的模型数量我大概会工作到地球毁灭的那一天。于是我找到了谷歌地图（[Google Map API](https://developers.google.com/maps/documentation/gaming)），强大的SDK允许我在Unity引擎内抓取地形与建筑信息用于生成模型，并基于经纬度做实时渲染。这为接下来的所有开发打下了基础。经过几周的文档阅读与范例学习（SDK的每一个feature都提供了一个Unity scene作为范例，感恩）终于实现了环境的渲染，并且实现了所有生成模型与平面（建筑，道路，水面）的分组归档，用于加入自定义材质与shader。

#### Firebase与Rest API

简单地教程学习和尝试MongoDB和自己Host SQL之后我还是选择了[Google FIrebase](https://firebase.google.com/)，因为其号称有打包好的Unity SDK。然而Firebase SDK for Unity只支持Android与ios系统，所以我不得不含泪点开Rest API开始学习，试图通过Rest API与云端服务器交互。万幸Unity有[RestClient Plugin](https://github.com/proyecto26/RestClient)用于便捷调用。

## 设计反思：

1.Connectivity作为设计的主要目标应该体现在游戏的所有方面，第一版设计的【让世界重焕生机】机制是玩家需要找到自己世界里当前区域的【生命核心】，激活并点亮颜色。搭建好后端服务器后【生命核心】功能完全被联机功能取代，核心思想是【所有玩家共享一个世界】，所以色彩和世界的状态应该由所有玩家共享。

<img src="/img/post1-10.png" alt="1" class="center" width="800"/>

2.玩家与世界的交互需要更多规则，无节制地种草会影响其他玩家游戏体验，并给服务器带来负担。需要更多设计引导玩家行为，逆向惩罚（游戏规则限制玩家能种草的上限）与正向鼓励（视觉设计让精心种植的植物有视觉冲击力，鼓励玩家种植前多思考）都需要更多设计

3.UI设计需要更多思考。当前版本的UI过于精简，在经纬度输入的过程中体验很糟糕。

<img src="/img/post1-1.png" alt="1" class="center" width="800"/>

4.色彩需要更多思考。当前版本的配色参考的是电子地图原色，确实过于丑陋了。

5.[背景音乐](https://myuu.bandcamp.com/track/home)的选择收到了所有应邀试玩的好朋友们的一致好评，在Immersive Environment构建过程中确实扮演了重要角色。

## 下一阶段目标：

1.更多联机功能与素材（WIP：花与树）

2.新的Shader与材质优化美术表现

3.更多UI设计

4.服务器优化为接下来的实时联机打下基础

5.更加细化下一步开发计划并实验确定技术使用

## 结语
总体来说我十分满意这个项目从立项到今天的所有进度和我的个人进步，也感谢Ruiz教授、其他前辈们和好朋友们的所有鼓励与指导。作为内容输出者承蒙厚爱。希望游戏作为媒介可以在困难时期给大家传递能量，也希望我的个人经验分享可以抛砖引玉，给同为游戏开发者的朋友们带来灵感，一同进步。感恩！

最后一起享受游戏吧！[游戏当前版本Demo](https://jingyu1999.itch.io/voyage) 