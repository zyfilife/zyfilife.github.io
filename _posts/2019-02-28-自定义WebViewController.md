---
layout: post
title: "自定义WebViewController" 
tag: iOS
---
### 准备所有UI控件
- webView
```swift
lazy var webView: WKWebView = {
        let config = WKWebViewConfiguration()
        config.userContentController = WKUserContentController()
        let view = WKWebView(frame: CGRect.zero, configuration: config)
        view.uiDelegate = self
        view.navigationDelegate = self
        return view
    }()
```
- progressView
```swift
lazy var progressView: UIProgressView = {
        let progressView = UIProgressView()
        progressView.progressTintColor = .green
        progressView.progressViewStyle = .bar
        progressView.progress = 0.0
        return progressView
    }()
```
- closeButton
```swift
lazy var closeButton: UIBarButtonItem = {
        let button = UIBarButtonItem(title: "关闭", style: UIBarButtonItemStyle.plain, target: self, action: #selector(MYWebViewController.closeAction(_:)))
        return button
    }()
```
- goBackButton
```swift
 lazy var goBackButton: UIBarButtonItem = {
        let button = UIBarButtonItem(title: "返回", style: UIBarButtonItemStyle.plain, target: self, action: #selector(MYWebViewController.goBackAction(_:)))
        return button
    }()
```

### 外部URL传入
```swift
public var url: URL?
```
### 控制progressView
```swift
fileprivate var progress: Float {
        get {
            return self.progressView.progress
        }
        set {
            if newValue >= 1.0 {
                self.progressView.alpha = 0.0
            }else {
                self.progressView.alpha = 1.0
            }
        }
    }
```
### 控制closeButton
```swift
 fileprivate var showClosedButton = true {
        didSet {
            guard self.isViewLoaded else {
                return
            }
            if self.showClosedButton {
                self.navigationItem.leftBarButtonItems = [self.goBackButton, self.closeButton]
            }else {
                self.navigationItem.leftBarButtonItems = [self.goBackButton]
            }
        }
    }
```