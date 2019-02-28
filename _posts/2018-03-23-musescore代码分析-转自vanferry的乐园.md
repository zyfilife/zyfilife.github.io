---
layout: post
title: "MuseScore代码分析-转自vanferry的乐园"
summary: 公司项目需要用到这款开源软件的导出曲谱功能，因此在此记录下别人的源码分析心得
featured-img: emile-perron-190221
---

# MuseScore的歌曲结构

 本文内容指的是musescore歌曲的内存表示形式，不涉及musescore文档格式的分析。musescore的文档是一种压缩了的xml文件，据说sibelius也是这样做的。

一首歌曲包含的数据都存放于`Score`类。
不过该类是一个巨类，除了基础数据外，还包含了乐谱排版，文件或数据流IO，以及所有的编辑功能。
musescore软件这种形式很常见，即是一个多文档编辑器MDI，它打开的每一个乐谱是一个MdiChild。
可以把它看成是一个乐谱文件对应的控件，即MdiChild窗口内嵌的那块区域，其父容器ScoreView即是MdiChild。

```c++
    Score内含：
    {
　　  QList<Part*> _parts,  // 乐器，
　　  QList<Staff*> _staffs,  // staff代表一行乐谱，一件乐器可能对应一个或2个（treble-base）staff，支持鼓谱，tab等，还未支持简谱
　　  MeasureBaseList _measures,  // 小节，每一个Measure代表从上到下的一列小节
　　  QList<Element*> _gel,  // 全局元素，如Slur, SLine
　　  QList<Beam*> _beams,  // 公用符尾，也是一种全局的数据
　　  RepeatList* repeatList,  // 反复记号
　　  AL::TimeSigMap* _sigmap, // 拍号
　　  AL::TempoMap* _tempomap// 速度
　　}
　　
　　Measure继承自MeasureBase，指的是从上到下的一列小节，内部的每个元素自己记住所属的track，内含：
　　{
　　ElementList _el, // 元素列表
　　QList<MStaff*> staves, // 每个staff有一个对应数据
　　QList<Tuplet*> _tuplets, // 多连音符，单独记录
　　Segment* _first, Segment* _last // 组成一个Segment链表，大部分数据都放在这里
　　}
　　
　　Segment保存了Staff里的所有数据。每一个Segment有固定的类型，内含的所有元素类型相同，且起点tick相同。
　　enum SegmentType
　　{
　　 SegClef,
　　 SegKeySig,
　　 SegTimeSig,
　　 SegStartRepeatBarLine,
　　 SegBarLine,
　　 SegGrace,
　　 SegChordRest,
　　 SegBreath,
　　 SegEndBarLine,
　　 SegTimeSigAnnounce,
　　 SegKeySigAnnounce
　　 };
```
歌曲的音符等信息都存放在Segment里。
就目前为止我对Segment列表和_el的理解，segment列表是为了排版用的，把元素按时间位置分组，这样排版时就可以快速定位元素，方便访问，同时提高效率。
