---
layout: default
title: 架构设计、详细设计（BCE方法）到应用程序框架映射指南
author: 戈、罗
---

# 架构设计、详细设计（BCE方法）到应用程序框架映射指南
{:.no_toc}

* 目录
{:toc}

## 逻辑架构

逻辑架构由四层模型（表示层、业务层、服务层、持久化层）构成

### 表示层

- 商家端使用 Web 作为表示层，提供餐厅信息管理子系统、菜品管理系统、用户管理系统、订单管理子系统、收入统计子系统
- 顾客端使用微信小程序作为表示层，提供取号排队子系统、用户点餐子系统、用户订单子系统、点评打分子系统

### 业务层

服务器充当业务层的角色，为表示层的各个子系统提供相应的服务模块，翻译用户的输入并依照用户的输入调用服务

### 服务层

从各种数据访问对象检索和创建模型，更新各个存储库的值，执行特定于应用程序的逻辑和操作等。

### 持久化层

MySQL 提供了数据的持久化服务

## 框架目录设计

### 小程序

```
.
├── app.js
├── app.json
├── app.wxss
├── components
│   ├── cart
│   │   ├── bar.js
│   │   ├── bar.json
│   │   ├── bar.wxml
│   │   ├── bar.wxss
│   │   ├── count-picker.js
│   │   ├── count-picker.json
│   │   ├── count-picker.wxml
│   │   ├── count-picker.wxss
│   │   ├── list.js
│   │   ├── list.json
│   │   ├── list.wxml
│   │   ├── list.wxss
│   │   ├── modal
│   │   │   ├── select-customer-count.js
│   │   │   ├── select-customer-count.json
│   │   │   ├── select-customer-count.wxml
│   │   │   └── select-customer-count.wxss
│   │   ├── specification.js
│   │   ├── specification.json
│   │   ├── specification.wxml
│   │   ├── specification.wxss
│   │   ├── submit-order-bar.js
│   │   ├── submit-order-bar.json
│   │   ├── submit-order-bar.wxml
│   │   └── submit-order-bar.wxss
│   ├── food
│   │   ├── category-list.js
│   │   ├── category-list.json
│   │   ├── category-list.wxml
│   │   ├── category-list.wxss
│   │   ├── menu-list-item.js
│   │   ├── menu-list-item.json
│   │   ├── menu-list-item.wxml
│   │   ├── menu-list-item.wxss
│   │   ├── menu-list.js
│   │   ├── menu-list.json
│   │   ├── menu-list.wxml
│   │   ├── menu-list.wxss
│   │   ├── search-box.js
│   │   ├── search-box.json
│   │   ├── search-box.wxml
│   │   └── search-box.wxss
│   └── iview
├── config.js
├── config.server.default.js
├── config.server.js
├── pages
│   ├── food
│   │   ├── cart.js
│   │   ├── cart.json
│   │   ├── cart.wxml
│   │   ├── cart.wxss
│   │   ├── detail.js
│   │   ├── detail.json
│   │   ├── detail.wxml
│   │   ├── detail.wxss
│   │   ├── menu.js
│   │   ├── menu.json
│   │   ├── menu.wxml
│   │   ├── menu.wxss
│   │   ├── search.js
│   │   ├── search.json
│   │   ├── search.wxml
│   │   └── search.wxss
│   ├── index
│   │   ├── index.js
│   │   ├── index.json
│   │   ├── index.wxml
│   │   └── index.wxss
│   ├── order
│   │   ├── comment.js
│   │   ├── comment.json
│   │   ├── comment.wxml
│   │   ├── comment.wxss
│   │   ├── detail.js
│   │   ├── detail.json
│   │   ├── detail.wxml
│   │   ├── detail.wxss
│   │   ├── index.js
│   │   ├── index.json
│   │   ├── index.wxml
│   │   └── index.wxss
│   └── queue
│       ├── index.js
│       ├── index.json
│       ├── index.wxml
│       └── index.wxss
├── project.config.json
├── service
│   ├── auth.js
│   ├── cart.js
│   ├── category.js
│   ├── customer.js
│   ├── desk.js
│   ├── food.js
│   ├── order.js
│   └── util.js
└── utils
    └── util.js
```

### 后端

```
.
├── app
│   ├── controller
│   │   ├── auth.js
│   │   ├── category.js
│   │   ├── desk.js
│   │   ├── desk_type.js
│   │   ├── file.js
│   │   ├── food.js
│   │   ├── order.js
│   │   └── specification.js
│   ├── middleware
│   │   └── auth.js
│   ├── model
│   │   ├── category.js
│   │   ├── comment.js
│   │   ├── customer.js
│   │   ├── desk.js
│   │   ├── desk_type.js
│   │   ├── file.js
│   │   ├── food_category.js
│   │   ├── food_comment.js
│   │   ├── food_image.js
│   │   ├── food.js
│   │   ├── order_item.js
│   │   ├── order.js
│   │   ├── specification.js
│   │   └── staff.js
│   ├── public
│   ├── router.js
│   └── service
│       ├── auth.js
│       ├── desk.js
│       ├── food.js
│       └── order.js
├── app.js
├── appveyor.yml
├── config
│   ├── config.default.js
│   ├── config.local.js
│   └── plugin.js
├── package.json
└── README.md
```

## 与 ECB 关系

ECB中：

- Entity：代表系统数据，如：顾客、订单、菜品等
- Boundary：与用户的接口，如：界面、网关、代理等
- Controller：连接 Boundary 和 Entity 的媒介，编排来自 Boundary 的命令的执行

Entity 包含：

- 服务器框架目录设计中，`model` 目录下定义了所有服务器与 MySQL 相关的实体，承载系统数据

Controller 包含：

- 服务器框架目录设计中，`controller` 目录下定义了所有的相关内容，它们接收来自上述 Boundary 的命令，并调用 `service` 的对象来获取或更新模型或其他请求。
- 服务器框架目录设计中，`service` 目录下定义了部分相关内容，封装可能在控制器中的所有业务逻辑。这样，控制器就在那里转发和控制执行。

在本系统中，Boundary有三个部分：

- 商家端 Web 程序用户界面
- 顾客端小程序用户界面
- 服务端 Nginx 反向代理服务器
