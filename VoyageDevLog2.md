---
layout: page
title: Voyage Devlog 2 - MMO初尝试
genre: Devlog
permalink: /VoyageDevLog2/
---

<div id="google_translate_element"></div>

<script type="text/javascript">
function googleTranslateElementInit() {
  new google.translate.TranslateElement({pageLanguage: 'zh'}, 'google_translate_element');
}
</script>

<script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>

[Devlog 1 - 新手上路请多指教](http://jingyuzhuang.top/VoyageDevLog1/)

[游戏当前版本Demo](https://jingyu1999.itch.io/voyage) 

## 导语：新的四周

立项开发四周写了第一篇Dev Log，现在离上次的Dev Log又过去了四周。这段时间的进度大概已经可以支撑起新的一篇Dev Log的内容，并且四周应该也是一个不错的周期来记录一些开发日常，正好在美国无尽的居家隔离期间除了看日历又能多一个方法，让我确切地感受到自己没有活在【土拨鼠日】。

过去的四周与之前【想到什么做什么】的摸索阶段比起来多了一些明确的目的性，在实现大量联机功能之余把时间都花在了饱受吐槽的UI/UX上，旨在给频繁捧场试玩的好朋友们提供一个更好的游戏体验。

## Voyage有了什么改变

沿用上一次Dev Log的定义：

> Voyage是一个精神世界的出游体验，它可以根据玩家输入的经纬度带领玩家前往任意的地球角落，并且根据玩家的位置进行实时生成周围环境。所以它是一个五亿平方公里的开放世界——整个地球的表面积。同时它也是一个虚拟的共享世界——玩家可以在这个虚拟的环境里遇到其他玩家，分享景色、合影、并共同留下自己的记号。

机制方面，五亿平方公里的世界没有改变，但是加入了更多的玩法与规则让玩家能更好地享受这个庞大的开放世界。这些玩法包括：

1.玩家可以种下小花和树。这些植物会记录瞬间，永远留在世界里，供其他玩家欣赏。

<img src="/img/PlantTree.gif" alt="1" class="center" width="800"/>

<img src="/img/PlantFlower.gif" alt="1" class="center" width="800"/>

2.完全的实时联机。玩家可以遇见世界里的朋友与陌生人，共享旅程。

<img src="/img/MultiPlayer.gif" alt="1" class="center" width="800"/>

3.账号、等级与统计系统。所有注册玩家都会有自己的账号统计数据，用自己的里程积累经验，种植更多的色彩。

<img src="/img/LevelUp.gif" alt="1" class="center" width="800"/>

视觉体现与UI/UX方面：

4.重新编写的Shader与Post Processing逻辑，空旷黑白的世界会在玩家走过并且留下植物之后重新焕发生机，加入更多色彩。

<img src="/img/ColorChange.gif" alt="1" class="center" width="800"/>

5.在引导界面嵌入了完整的谷歌地图作为背景

<img src="/img/GoogleMapUI.gif" alt="1" class="center" width="800"/>

6.完整的UI轮盘系统搭载各种游戏功能

<img src="/img/Panel.gif" alt="1" class="center" width="800"/>

7.加入了类似导航系统的平面小地图

<img src="/img/MiniMap.gif" alt="1" class="center" width="800"/>

## 除去【享受单人开发】这个最重要的一点之外的一点经验分享：

#### 数据结构

这是我的第一次【大型多人联机】尝试。所以在最初设计【玩家信息】和【玩家放置物】等等的数据结构时有很多不周全的地方，导致每一次数据结构的更新都要进行大规模的删档和数据库调整。在这方面想的过于简单了，还需要大量的学习与练习。好在[Google Firebase](https://firebase.google.com/)提供了对萌新极为友好的图形界面，让我在与数据库与数不清的JSON文件打交道时节约了很多时间成本。

#### 浏览器嵌入

Google地图的嵌入是一个复杂的过程，多次尝试手敲代码无果后还是选择了购买Asset Store的[Embedded Browser](https://assetstore.unity.com/packages/tools/gui/embedded-browser-55459)。提供了包括Windows和MacOS在内的多平台支持，彳亍！

#### 轮盘UI

【轮盘UI】是让我最始料未及的困难。从GTA5，DOTA2玩到最近在体验的原神，我一直是【轮盘UI】的忠实粉丝。这次在仿制UI的时候仔细研究了一番才发现轮盘UI比我想象的要难实现。一番瞎折腾过后倒是实现了我目前为止仍不确定是不是粗暴解的实现方法，不过手感倒是和我印象中的轮盘UI差别不大了。

<img src="/img/post2-1.png" alt="1" class="center" width="800"/>

（如图，将屏幕划分为八等分区分鼠标位置对应轮盘格）

## 设计反思：

1.机制

> 玩家与世界的交互需要更多规则，无节制地种草会影响其他玩家游戏体验，并给服务器带来负担。需要更多设计引导玩家行为，逆向惩罚（游戏规则限制玩家能种草的上限）与正向鼓励（视觉设计让精心种植的植物有视觉冲击力，鼓励玩家种植前多思考）都需要更多设计

加入等级系统和【里程兑换经验值】的机制后问题得到了初步解决，但在【升级所需经验数值】与【货币发放效率】上还需多斟酌

2.UI

> UI设计需要更多思考。当前版本的UI过于精简，在经纬度输入的过程中体验很糟糕。

新版的UI也初步解决了一部分易用性的问题，但是更多细节是否合理还需要更多的Playtest验证

3.色彩

> 色彩需要更多思考。当前版本的配色参考的是电子地图原色，确实过于丑陋了。

连续看了几周Color Theory相关教学视频后做出了一版我觉得有一定改进的色卡，现在的颜色处理稍微柔和了一些，搭配Post Processing看起来应该不算太糟

4.跳跃与飞行

跳跃与飞行的取舍方面参考了很多朋友的意见后还是保持了玩家的自由选择。飞行的核心体验是【以Top Down视角俯瞰风景】而并非【位移】。所以要彻底取代飞行必须要加入能满足这点需求的机制，还需要进一步考虑。

## 下一阶段目标：

1.更多的创作空间。下一阶段会加入的是类似MineCraft的自定义留言牌，让玩家有更多UGC向体验。

2.更多的社交向交互功能。下一阶段会加入的是参考[死亡搁浅](https://zh.wikipedia.org/wiki/%E6%AD%BB%E4%BA%A1%E6%93%B1%E6%B7%BA)社交系统的【点赞】功能，玩家之间可以相互点赞对方的创作，并且收获/给出的赞会提高玩家等级。在促进交互的同时让玩家有多一个维度的等级数值积累。

3.尝试解决Google Map SDK在大陆地区的支持问题。

## 结语

编写Dev Log是一个很好的机会，它让我花一段时间总结归纳自己的成功与不足并且制定一些阶段性目标。而有【目标】有【需求】的设计与开发也让我有了更多的Problem Solving方面感悟，在不断地迭代中解决遗留问题，加入新鲜元素。

最后继续感谢大家的鼓励和试玩，课堂里的同学教授们和网络上的好朋友们的好评和鼓励让我诚惶诚恐。还是会继续学习与开发，争取在明年能带着这个项目在一些indie评选与大家见面。承蒙厚爱！（深鞠一躬）

一起享受游戏吧！[游戏当前版本Demo](https://jingyu1999.itch.io/voyage) 
