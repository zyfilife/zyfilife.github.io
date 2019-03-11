---
layout: post
title: "MYSheetView"
tags: iOS
editor: 朱益锋
---
> 引言：提供自定义的转场方式，支持五个方向，支持自定义宽高，同时在源码中还可以自定义弹出动画

<p style="text-align: center;"><img src="/assets/img/posts/MYSheetView/MYSheetView.gif" alt="效果图"></p>

## 使用方法
- 下载源代码[MYSheetView](https://github.com/zyfilife/MYSheetView)
- 使用storyboard或者纯代码创建一个presentedViewController, 就像下面这样
```swift
import UIKit
class DatePickerViewController: UIViewController {
	@IBOutlet weak var sureButton: UIButton!
	@IBOutlet weak var titleLabel: UILabel!
	@IBOutlet weak var cancelButton: UIButton!
	@IBOutlet weak var datePicker: UIDatePicker!

	var name: String?
	var currentDate: Date?

	override func viewDidLoad() {
		super.viewDidLoad()
		self.titleLabel.contentMode = .bottom
		self.titleLabel.text = self.name != nil ? self.name!: nil
		self.datePicker.date = self.currentDate != nil ? self.currentDate!: Date()
	}

	@IBAction func clickCancelAction(_ sender: UIButton) {

	}

	@IBAction func clickSureButtonAction(_ sender: UIButton) {

	}
```

- 在presentingViewController中，添加以下代码
```swift
@IBAction func showDatePicker(_ sender: UIButton) {
	let viewController = MainHelper.instantiateViewControllerWithIdentifier(MainHelper.kDatePickerViewController) as! DatePickerViewController
	viewController.name = "DatePicker"
	viewController.currentDate = nil
	//自定义方向
	self.slideInPrensentationDelegate.direction = self.direction
	//自定义宽高，左右方法时，设置宽有效，上下方向时，设置高有效，中心弹出时，两者都有效
	self.slideInPrensentationDelegate.customHeight = 260
	self.slideInPrensentationDelegate.customWidth = self.view.frame.size.width - 50*2
	self.slideInPrensentationDelegate.disableCompactHeight = true
	viewController.transitioningDelegate = self.slideInPrensentationDelegate
	viewController.modalPresentationStyle = .custom
	self.present(viewController, animated: true, completion: nil)
}
```