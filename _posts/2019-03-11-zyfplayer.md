---
layout: post
title: "ZYFPlayer"
tags: iOS 基于AVPlayer
editor: 朱益锋
---
> 引言：Swift写的基于AVPlayer的音视频播放器, 支持自定义播放视图，提供播放器的多种回调

<p style="text-align: center;"><img src="/assets/img/posts/ZYFPlayer/ZYFPlayer.gif" alt="效果图"></p>

## 源码解析
- 项目地址：[ZYFPlayer](https://github.com/zyfilife/ZYFPlayer)
- ZYFPlayerTrack: 可以理解为将一个播放事件包装成一个类，包含了视频网址，视频总时长，当前播放时间，是否播放结束等等属性
- ZYFPlayer: 核心播放类。系统AVPlayer,并没有直接提供播放事件的回调方法，因此我们需要通过KVO监听AVURLAsset、AVPlayer以及AVPlayerItem，来实现以下回调
	```swift
	@objc protocol ZYFPlayerDelegate: NSObjectProtocol {
	@objc optional func zyf_player(player: ZYFPlayer, shouldPlayTrack track: ZYFPlayerTrack) -> Bool
	@objc optional func zyf_player(player: ZYFPlayer, willPlayTrack track: ZYFPlayerTrack)
	@objc optional func zyf_player(player: ZYFPlayer, didEndToPlayTrack track: ZYFPlayerTrack)
	@objc optional func zyf_player(player: ZYFPlayer, shouldChangeToState toState: ZYFPlayerState) -> Bool
	@objc optional func zyf_player(player: ZYFPlayer, track: ZYFPlayerTrack, willChangeToState toState: ZYFPlayerState, fromState: ZYFPlayerState)
	@objc optional func zyf_player(player: ZYFPlayer, track: ZYFPlayerTrack, didChangeToState toState: ZYFPlayerState, fromState: ZYFPlayerState)
	@objc optional func zyf_player(player: ZYFPlayer, track: ZYFPlayerTrack, didUpdateCurrentTime currentTime: TimeInterval)
	@objc optional func zyf_player(player: ZYFPlayer, track: ZYFPlayerTrack, didUpdateBufferTime bufferTime: TimeInterval)
	@objc optional func zyf_player(player: ZYFPlayer, track: ZYFPlayerTrack, receivedTimeout timeOut: ZYFPlayerTimeOut)
	@objc optional func zyf_player(player: ZYFPlayer, track: ZYFPlayerTrack, receivedErrorCode errorCode: ZYFPlayerErrorCode, error: Error?)
	}
	```
	
- ZYFPlayerView: 播放器展示和控制视图。你可以在这个类中添加或修改各个UI控件，并实现ZYFPlayer的代理方法。同时你可以将以下的按钮点击事件通过代理的方式交给视图控制器处理
	```swift
	protocol ZYFPlayerViewDelegate: NSObjectProtocol {
    func zyf_player(playerView: ZYFPlayerView, didClickPlayButton sender: UIButton)
    func zyf_player(playerView: ZYFPlayerView, didClickCloseButton sender: UIButton)
    func zyf_player(playerView: ZYFPlayerView, didClickFullScreenButton sender: UIButton)
    func zyf_player(playerView: ZYFPlayerView, didChangeControlViewDisplay isHiddenControlView: Bool)
	}
	```
	
## 使用方法
- 在ViewController中声明一个ZYFPlayerView对象，遵守ZYFPlayerViewDelegate,并实现代理方法
- 在viewDidLoad方法中实例化播放器，并且传递视频的URL，你也可以重写ZYFPlayerView的实例化方法，传递一个视频的数据模型对象
	```swift
	override func viewDidLoad() {
        super.viewDidLoad()
        let url = URL(string: "")
        self.playerView = ZYFPlayerView(streamURL: url, delegate: self)
        self.view.addSubview(self.playerView!)
    }
    
    override func viewDidLayoutSubviews() {
        super.viewDidLayoutSubviews()
		//设置视频播放视图的frame
        self.playerView?.frame = self.view.bounds
    }
	```