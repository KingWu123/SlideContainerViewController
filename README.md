# SlideContainerViewController
implement a containerViewController,   has  two child viewController  slide right-left, can use gesture to show each other.

##Installation
将工程里的
SlideContainerViewController.h,
SlideContainerViewController.m, 
UIViewController+SlideContainerViewController.h,
UIViewController+SlideContainerViewController.m
这四个文件拷到自己的工程里

##How to use
UIViewController *leftVC  = ....

UIViewController *rightVC = ....

SlideContainerViewController *slideContainerVC =  [[SlideContainerViewController alloc]initWithRightViewController:rightVC withLeftViewController:leftVC];

默认显示的是RightVC

##Release Notes
####version 1.0
手势跟随做动画时，将新进来的界面截了图，与老的vc.view做动画.

###version 1.1
不再用截图来做手势跟随的动画，而是直接用子view,
这样调用的方式跟系统的NavigationController手势跟随是一样的，即


oldVC            newVC
手势跟随开始:
willDisAppear    
				willAppear

a)手势跟随结束， 新界面展示：
did DisAppear
               didAppear
               
b)手势跟随结束，新界面没有打开：
				willDisAppear
				didDisAppear
willAppear
didAppear