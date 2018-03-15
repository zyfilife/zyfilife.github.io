---
layout: post
title: "曲谱弹奏代码设计"
summary: 由于曲谱弹奏界面一个视图控制器文件代码量达到了2000行，因此决定对该界面的代码进行重新设计
featured-img: emile-perron-190221
---
## 层级划分
> ### 视图层
- ##### 控制视图层
    
> NavigationBar
    
> ToolBar
    
    > KeyboardView
    
- ##### 显示视图层
    
    > ScoreView
    
    > ReadyPlayView
    
2. ### 功能控件层
    > mainDisplayLink
    > coolDownDisplayLink
    > metronomeTimer
    > player
    > metronomePlayer
    > coolDownPlayer
3. ### 数据层
    > 弹奏配置参数
    > 弹奏数据记录
    > 弹奏数据处理
## 层级关联
1. 控制视图
    > 操作功能控件
    > 设置弹奏配置参数
    > 更新弹奏数据
2. 数据层
    > 被控制视图和功能控件更新
    > 做处理
3. 显示层
    > 根据数据做实时更新

## 设计思路
1. 创建曲谱弹奏视图控制器
2. 视图控制器拥有

    > 控制视图对象
    
    > 显示视图对象
    
    > 数据模型对象
    
    > 一系列功能控件
    
3. 控制视图对象通过代理将控制事件传递给视图控制器
4. 数据模型对象接收控制事件处理数据
5. 显示视图接收最新的数据更新视图

