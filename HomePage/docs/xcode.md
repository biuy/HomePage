# xcode 文档英文笔记

找到了xcode的英文文档的正确打开方式

## Required Resources
Every UIKit app is required to have the following resources:

	*	App icons
	* 	Launch screen storyboard

The *LaunchScreen.storyboard* file contains your app’s initial user interface, and it can be a splash screen or a simplified version of your actual interface.

The launch screen also provides cover for your app while it initializes itself. 

## Required App Metadata

your app’s configuration and capabilities are in *Info.plist*

Xcode provides a preconfigured version of this file with every new project template.


## Code Structure of a UIKit App
Model-View-Controller (MVC) design pattern

UIKit provides a *UIDocument* object for organizing the data structures that belong in a disk-based file.

Specifically, UIKit defines the *UIView* class, which is usually responsible for displaying your content onscreen. 

