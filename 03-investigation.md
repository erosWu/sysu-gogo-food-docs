---
layout: default
title: 项目前期调研
author: 戈、高
---

# 项目前期调研
{:.no_toc}

作者：调研组

* 目录
{:toc}

# 项目前期调研

## 背景

目前市面上越来越多商户使用扫码点餐，但按照商家自身定位以及需求各个商家的扫码点餐功能都有各自的特点。因此我们调研了一些市面上具有代表性的商家，对他们点餐相关的软件应用进行竞品分析，力求探索一种适用于常规小餐店的点餐服务程序，确定必须服务和优化用户体验的服务。

## 交互设计与技术分析

针对扫码点餐的核心业务，我们挑选了美团点评智慧餐厅、南京大排档、CoCo都可手机点餐小程序三款竞品做了详细的交互过程与功能架构设计做了分析。

### 功能框架

![南京大排档][1]

南京大排档分析：

 - 没有悬浮窗购物车，查看明细和调整点餐需要切换较麻烦
 - 不自动保存已点菜单

 ![美团][2]
 
美团点评智慧餐厅分析（商家米仓食堂为例）：

 - 单一菜品有非常详尽的需求设定，有悬浮窗的购物车
 - 整体流程清晰明确

![COCO][3]

COCO分析：

 - 整体流程清晰明确
 - 使用场景就是到店取餐，分预订和即时两种，没有外卖，因此功能设计算是清晰合理，没有多余的界面和操作环节
 - 作为快餐餐饮，经常存在某连锁店某产品缺货但依旧可以被点的情况，即没有对具体商铺提供的产品种类的个性化设置

### 交互体验

***核心流程的界面截图在附录给出***

#### **南京大排档**

 - 贴图很粗糙，菜品图片分辨率较低，拍摄水平较差
 - 有预约功能，但部分店面不开放
 - 取号等待过程可以点餐，但是必须分配到桌子后才能下单

#### **美团点评智慧餐厅**

 - 界面整体整洁，配色舒适
 - 架构清晰合理，交互上也比较符合用户习惯
 - 缺少个人中心
 - 选择就餐人数意义不明

#### **COCO**

 - 白橙色调同品牌logo
 - 架构清晰合理，交互上也比较符合用户习惯

### 亮点特点借鉴

#### **南京大排档**

 - 取号点餐，分配到桌再下单，这个设定可以节省点餐用时

#### **美团点评智慧餐厅**
 
 - 店内搜索功能
 - 首页的菜品图片较真实、有吸引力
 - 美团自身的优惠券可以使用，支付后也会有优惠券奖励

#### **COCO**

 - 顾客可以根据不同场景选择门店和取餐时间，免去排队点餐项
 - 会把促销产品提前到最前面鼓励消费
 - 赠送限工作日使用的优惠券，拉动非节假日的消费

## 总结

综合前面调研的各个产品的优势和特点，我们需要完成的产品需要更为细致的考虑到用户的需要。

在取号等待的过程中，借鉴南京大排档的亮点可以提前点单，分配到桌子后下单，由此可以节省点餐用时，还可以统计出下单/点餐率从而计算调整准备菜品种类数量；

点餐界面用瀑布流方式展示菜品，借鉴COCO，可以根据评分或者主推，将招牌菜等提前，便于用户找到；

更关注售后，对菜品开启评分系统，由此可以统计出用户喜好，制定个性化菜单推荐，调整进购材料的种类和数量。借鉴美团，制定优惠价等鼓励回头客和提升淡季销售。

## 附录

**美团点评智慧餐厅**：点餐-选择规格-选择人数-确认下单-支付完成

![此处输入图片的描述][4]
![此处输入图片的描述][5]
![此处输入图片的描述][6]
![此处输入图片的描述][7]
![此处输入图片的描述][8]
![此处输入图片的描述][9]
优惠券
![此处输入图片的描述][10]
菜品详情
![此处输入图片的描述][11]
菜品搜索
![此处输入图片的描述][12]
![此处输入图片的描述][13]
餐后点评
![此处输入图片的描述][14]

**南京大排档**：选择城市、门店-选择人数-排队取号
![此处输入图片的描述][15]
![此处输入图片的描述][16]
![此处输入图片的描述][17]
![此处输入图片的描述][18]
点餐
![此处输入图片的描述][19]
点菜清单
![此处输入图片的描述][20]

**COCO**：个人订单
![此处输入图片的描述][21]
选择门店-点餐-选择规格-购物车-提交订单-结算
![此处输入图片的描述][22]
![此处输入图片的描述][23]
![此处输入图片的描述][24]
![此处输入图片的描述][25]
![此处输入图片的描述][26]
按单号领取
![此处输入图片的描述][27]


  [1]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/%E5%9B%BE%E7%89%873.1.png
  [2]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/%E5%9B%BE%E7%89%871.1.png
  [3]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/%E5%9B%BE%E7%89%872.2.png
  [4]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/4.jpg
  [5]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/11.jpg
  [6]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/6.jpg
  [7]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/7.jpg
  [8]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/8.jpg
  [9]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/15.jpg
  [10]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/9.jpg
  [11]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/10.jpg
  [12]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/12.jpg
  [13]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/14.jpg
  [14]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/16.jpg
  [15]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/19.jpg
  [16]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/20.jpg
  [17]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/22.jpg
  [18]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/18.jpg
  [19]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/24.jpg
  [20]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/25.png
  [21]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/27.png
  [22]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/28.png
  [23]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/29.png
  [24]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/30.png
  [25]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/31.png
  [26]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/32.png
  [27]: https://raw.githubusercontent.com/FateStonesGate/MarkdownPhoto/master/33.png
