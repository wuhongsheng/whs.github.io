---
layout: post
title:  "React Native从入门到放弃"
date:   2017-07-23 08:14:54
categories: 跨平台
tags:  ReactNative 跨平台
author: WHS
---

* content
{:toc}

[React Native](http://facebook.github.io/react-native/) 开发指南

使用JavaScript和React构建本地移动应用程序
React Native允许您仅使用JavaScript构建移动应用程序。它使用与React相同的设计，让您从声明组件构成丰富的移动UI。




## 环境配置

```
1.安装node.js

2.安装react-native命令行工具
npm install -g react-native-cli

3.新建项目
react-native init [ProjectName]
```

## 常用命令


#### [升级新版本](http://reactnative.cn/docs/0.46/upgrading.html)

```

1. 安装Git并设置环境变量

2. 安装react-native-git-upgrade工具模块
 $npm install -g react-native-git-upgrade

3. 进入项目目录下运行更新命令
 $ react-native-git-upgrade
 这样会直接把react native升级到最新版本
 或者是：
 $ react-native-git-upgrade X.Y.Z
 这样把react native升级到指定的X.Y.Z版本
```

#### 降级版本

```
npm install --save react-native@版本号。
通过上诉操作之后，别忘了更新一下模板。
react-native upgrade
```

#### 运行调试方法

```
To run your app on iOS:
   cd /Users/whs/AwesomeProject
   react-native run-ios
   - or -
   Open ios/AwesomeProject.xcodeproj in Xcode
   Hit the Run button
To run your app on Android:
   cd /Users/whs/AwesomeProject
   Have an Android emulator running (quickest way to get started), or a device connected
   react-native run-android

Google浏览器调试地址
http://localhost:8081/debugger-ui   
```
#### [npm](https://www.npmjs.com/)常用命令
```
#更新
npm install npm@latest -g
```
---

## 参考资料

* [官网](http://facebook.github.io/react-native/)

* [写给移动开发者的 React Native 指南](http://www.jianshu.com/p/b88944250b25)

* [React Native 中文网](http://reactnative.cn/post/3634)

* [React](https://facebook.github.io/react/)

* [ReactNative组件生命周期](http://blog.csdn.net/ElinaVampire/article/details/51813677)



### 常用组件

* UI框架

  1.[React Native UI Toolkit](https://react-native-training.github.io/react-native-elements/)


* [mapbox/react-native-mapbox-gl](https://github.com/mapbox/react-native-mapbox-gl)

* [极光推送](https://github.com/jpush/jpush-react-native)

* 网络
  
  1.[fetch](https://github.com/github/fetch)


---

### 常见问题

**问题描述**

我是在Mac环境下，利用facebook开源的react-native创建原生app项目缓慢的问题

**解决办法**

```
1.确定自己的环境配置是否有问题
2.打开终端，输入命令行
brew install wget

3.npm config set registry=http://registry.npm.taobao.org/

```


**问题描述**
```
React Native unable to load script from assets index.android.bundle on windows
```
**解决办法**

```
1.在工程目录里建assets目录

2.运行命令
 react-native bundle --platform android --dev false --entry-file index.android.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res

3.运行程序
react-native run-android
```

**问题描述**

```
Installing build/Build/Products/Debug-iphonesimulator/SCLYGZ.app
An error was encountered processing the command (domain=NSPOSIXErrorDomain, code=2):
Failed to install the requested application
An application bundle was not found at the provided path.
Provide a valid path to the desired application bundle.
Print: Entry, ":CFBundleIdentifier", Does Not Exist
```

**解决方法**

使用Xcode打开项目运行解决问题

**问题描述**

```
Users/whs/Library/Developer/Xcode/DerivedData/SCLYGZ-cwawqpsnahyurjgkghwavkkokijl/Build/Intermediates.noindex/SCLYGZ.build/Debug-iphonesimulator/SCLYGZ.build/Script-00DD1BFF1BD5951E006B06BC.sh: line 3: ../node_modules/react-native/scripts/react-native-xcode.sh: No such file or directory
```

**解决方法**

change ../node_modules/react-native/packager/react-native-xcode.sh 
to ../node_modules/react-native/scripts/react-native-xcode.sh

Open in Xcode -> Select your Project -> "Build Phases" tab -> "Bundle React Native code and images"
Then change the above paths.

或者
```
rm -rf node_modules 
rm -rf ~/.rncache
npm install
```




```
error: bundling failed: "Unable to resolve module `parse/react-native` from `/Users/whs/ReactNative/GZLYCY/js/setup.js`: Module does not exist in the module map\n\nThis might be related to https://github.com/facebook/react-native/issues/4968\nTo resolve try the following:\n  1. Clear watchman watches: `watchman watch-del-all`.\n  2. Delete the `node_modules` folder: `rm -rf node_modules && npm install`.\n  3. Reset packager cache: `rm -fr $TMPDIR/react-*` or `npm start -- --reset-cache`."
```


