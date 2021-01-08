---
layout: post
title: The StockTracker as the ios Course Project
description: 参加CodePath的ios课程，并完成课程项目。
permalink: /codepath-project-stocktracker/
categories: [gadgets]
tags: [Bio, StockTracker, Course Project]
date: 2021-01-08 12:25:30
---

# 　

## 开端

2020年秋季学期开始前，我收到[CodePath](https://codepath.org/)的邮件邀请，参加了它们的ios课程。一学期的线上课程和期末project，让我对ios开发及swift语言有了初步的认识。此处不记录课程流程，只对资源进行总结

## 资源
- [代码完全开源](https://github.com/liecn/StockTracker)，注：本文内容于2020年12月6日测试并进入维护。

| <img src='https://github.com/liecn/ios_course/raw/main/imgs/demo_1_subtitle.gif' height="250"> | <img src='https://github.com/liecn/ios_course/raw/main/imgs/demo_2_subtitle.gif' height="250">|

- App的ui设计，制作[wireframe](https://www.figma.com/community)

| <img style="float: left;" src='https://github.com/liecn/ios_course/raw/main/imgs/wireframe.png' height="250">   | <img style="float: right;" src='https://github.com/liecn/ios_course/raw/main/imgs/wireframe.gif' height="250"> |

- Learn Swift Faster: [hackingwithswift](https://www.hackingwithswift.com/)

- 制作Gif: [giphy capture](https://giphy.com/apps/giphycapture)

- 协同编辑markdown: [hackmd](https://hackmd.io/)

## Points
### INDICATOR
- Use `@State` for simple properties that belong to a single view. They should usually be marked private.
- Use `@ObservedObject` for complex properties that might belong to several views. Any time you’re using a reference type you should be using @ObservedObject for it.
- Use `@EnvironmentObject` for properties that were created elsewhere in the app, such as shared data.
- Use `@Binding` since it lets us create a mutable value in a view, that actually points to some other value from elsewhere. In the case of Toggle, the switch changes its own local binding to a Boolean, but behind the scenes that’s actually manipulating the @State property in our view.
- `@Published` is one of the most useful property wrappers in SwiftUI, allowing us to create observable objects that automatically announce when changes occur.

### PROPERTIES
- Property Observers: There are two kinds of property observer: `willSet` and `didSet`, and they are called before or after a property is changed. In `willSet` Swift provides your code with a special value called `newValue` that contains what the new property value is going to be, and in `didSet` you are given `oldValue` to represent the previous value.
- Computed Properties: To make a computed property, place an open brace after your property then use either `get` or `set` to make an action happen at the appropriate time.


## End

Null
