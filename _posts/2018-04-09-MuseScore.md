---
layout: post
title: "MuseScore源码解析"
summary: 基于MuseScore2.0
featured-img: emile-perron-190221
--- 
### 基础知识准备
- C++语法
- QT框架
- 钢琴乐理知识
- [MuseScore用户手册](https://musescore.org/zh-hans/handbook/yonghushouce)

### 源码阅读方法
1. 找到入口函数，了解程序启动流程
2. 用Sublime Text打开曲谱源文件.mcxl查看其数据结构
3. 找到程序加载曲谱的函数，了解Score对象具体是怎么生成的
4. 找到导出XML文件的函数，了解其导出后的数据结构

### 源码解析
- MuseScore中曲谱的结构
![曲谱结构介绍](/assets/img/posts/2018-04-09-musescore源码解析/MuseScore.png)
	- 最普通的情况下, 一个Score对象由一条或二条Staff(五线谱)构成, Staff包含若干个Measure(小节),Measure包含若干个Segment(纵列), Segment包含Chord(和弦)或者Rest(休止符), Chord包含一个或若干个Note(音符), Chord也可能包含GraceNotes(装饰音和弦数组)
	
	- 从另一个角度看, 一个Score也可以看作一个RepeatList(重复弹奏小段数组)，RepeatList包含一个或者若干个RepeatSegment(重复弹奏的小段), RepeatSegment包含若干个Measure
	

- 部分对象、属性、方法
	- `Part` 用户手册中有介绍，大意是一个曲谱中可能会不同人或者乐器负责的部分，这时就用PartList区分开来。
	-  `TempoText` 拍子速度
	-  `TimeSig` 节拍
	-  `Fraction` 自定义用于描述分数的类
	-  `tick` 嘀嗒声，这里作为单位值，用来标记各类对象在时间轴上的位置
	-  `utick` 实际时间位置，一个重复小段第一次弹奏和第二次弹奏的`utick`不同，但`tick`相同
	-  `ticks()` 指该对象从开始到结束包含了多少个tick
	- `Measure* Score::tick2measure(int tick) const` 根据tick值获取对应的小节
	- `qreal RepeatList::utick2utime(int tick) const` 将实际tick转换为实际position
	- `voice` 声部。MuseScore定为4个声部
	- `track` 可以理解为音轨。五线谱数量乘以声部总数即为音轨总数
	- `Ms::Element* element(int track) const { return _elist.value(track);  }` 获取Segment上制定音轨的元素
	- 
	
最后附上[MuseScore源码](https://github.com/musescore/MuseScore/)

