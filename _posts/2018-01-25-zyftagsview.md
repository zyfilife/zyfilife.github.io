---
title: "ZYFTagsView"
date: 2018-01-25 19:32:32
editor: 朱益锋
---
## 控件介绍
- 单行
- 标签大小自适应
- 超出范围可滚动
- 分为纯文字、纯图片、文字加图片三种

## 文件介绍

- ### `ZYFTag`
    ```
    //让标签模型遵守本协议
    @protocol ZYFTag <NSObject, NSCopying, NSCoding>
    @property (nonatomic, strong, nullable, readonly) NSString *title;
    @property (nonatomic, strong, nullable, readonly) NSString *imagePath;
    @end
    ```
- ### `ZYFTagsViewCell`
    ```
    //单个标签视图
    @interface ZYFTagsViewCell : UIView
    @property (nonatomic, strong) UILabel *titleLabel;
    @property (nonatomic, strong) UIImageView *imageView;
    @property (nonatomic, assign) UIEdgeInsets edgeInsets;
    @property (nonatomic, assign) CGSize imageSize;
    @property (nonatomic, assign) CGFloat margin;
    @end
    
    //懒加载
    - (UILabel *)titleLabel
    {
        if (!_titleLabel) {
            _titleLabel = [[UILabel alloc] init];
            [self addSubview:_titleLabel];
        }
        return _titleLabel;
    }

    //懒加载
    - (UIImageView *)imageView
    {
        if (!_imageView) {
            _imageView = [[UIImageView alloc] init];
            [_imageView zyf_toCornerWithRadius:_imageSize.height/2];
            [self addSubview:_imageView];
        }
        return _imageView;
    }
    
    
    - (void)layoutSubviews
    {
        [super layoutSubviews];
        //判断控件是否存在
        if (_imageView && _titleLabel) {
            //设置控件Frame
        }else if (_titleLabel && !_imageView) {
            //设置控件Frame
        }else if (_imageView && !_titleLabel) {
            //设置控件Frame
        }
    }
    ```
- ### `ZYFDisposeTag`
    ```
    //根据标签模型生成包含`width` `originX`两个属性的配置模型
    ```


- ### `ZYFBaseTagsView` 
    
    ```
    //TagsView基类
    
    ```

- ### `ZYFTextTagsView`
    ```
    //纯文字的标签视图
    
    ```

- ### `ZYFImageTagsView` 
    ```
    //纯图片的标签视图
    
    ```

- ### `ZYFImageTextTagsView` 
    ```
    //文字加图片的标签视图
    
    ```
