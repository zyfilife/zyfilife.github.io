---
layout: post
title: "iOS学习笔记之@property" 
tag: iOS开发笔记
summary: 
featured-img: emile-perron-190221
---
- `strong`: 除NSString\block以外的OC对象
```
@property(nonatomic, strong) NSArray  *array;
```
- `weak`：各种UI控件(但不是绝对，也有控件要使用strong属性的)
``` 
@property (nonatomic, weak) UIButton *button;
```
- `assign`：CGFloat，NSInteger等基本数据类型、枚举、结构体（非OC对象）
```
@property(nonatomic, assign) CGFloat width;
```
- `copy`：
     `copy` : 创建的是不可变副本(如`NSString`、`NSArray`、`NSDictionary`)
     `mutableCopy` :创建的是可变副本(如`NSMutableString`、`NSMutableArray`、`NSMutableDictionary`)
```
@property(nonatomic, copy)NSString *string;
```

##### ARC
-  `copy` : 只用于`NSString` `block`
-  `strong` : 除`NSString` `block`以外的OC对象
-  `weak`: 当2个对象相互引用，一端用`strong`，一端用`weak`
- `assgin` : `基本数据类型`、`枚举`、`结构体`（非OC对象）