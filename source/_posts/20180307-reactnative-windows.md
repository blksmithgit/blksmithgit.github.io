---
title: windows下安装reactnative
date: 2018-03-07 11:27:24
tags: [reactnative,windows]
categories: 工具使用
---

## 安装依赖项
* Node 
* the React Native command line interface
* Python2 
* a JDK 
* Android Studio.


### 安装Chocolatey
chocolatey是windows平台下的包管理工具，类似mac下的homebrew，node.js的npm

安装：以管理员权限打开命令提示符窗口，然后输入一下命令并执行：

	@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
 ```

安装完成后，输入 

    choco

查看版本号

### 安装 Node, Python2, JDK
以管理员权限打开命令提示符窗口，然后输入以下命令并执行：
​    
    choco install -y nodejs.install python2 jdk8

## 安装React Native CLI
	npm install -g react-native-cli

### 新建一个项目

	react-native init <project name>

## 安装 React Native Windows
### 安装React Native Windows CLI
如果使用npm

	npm install --save-dev rnpm-plugin-windows
如果使用 Yarn,

	yarn add rnpm-plugin-windows --dev

### 初始化项目
Initialize your React Native Windows project in the project directory by running:

	react-native windows

在这一步报错了：
    Could not find react-native-windows@0.54.*. Latest version of react-native-windows is 0.52.0-rc.3, try switching to react-native@0.52.*.

版本不兼容，用react-native 0.52.0 重新创建项目

    react-native init --version="0.52.0" MyProject

然后进入项目目录，再来一遍
    npm install --save-dev rnpm-plugin-windows

再次执行
    react-native windows

这次成功了，显示如下：

    react-native-windows@0.52.0-rc.3 successfully installed.
    Generating self-signed certificate...
    Self-signed certificate generated successfully.
       create windows\.gitignore
       create windows\testrn\ReactAssets\.gitignore
       create App.windows.js
       create windows\testrn\App.xaml
       create windows\testrn\App.xaml.cs
       create windows\testrn\MainReactNativeHost.cs
       create windows\testrn\Package.appxmanifest
       create windows\testrn\Properties\AssemblyInfo.cs
       create windows\testrn\Properties\Default.rd.xml
       create windows\testrn\ReactAssets\index.windows.bundle
       create windows\testrn\testrn.csproj
       create windows\testrn.sln
       create windows\testrn\Assets\LockScreenLogo.scale-200.png
       create windows\testrn\Assets\SplashScreen.scale-200.png
       create windows\testrn\Assets\Square150x150Logo.scale-200.png
       create windows\testrn\Assets\Square44x44Logo.scale-200.png
       create windows\testrn\Assets\Square44x44Logo.targetsize-24_altform-unplated.png
       create windows\testrn\Assets\StoreLogo.png
       create windows\testrn\Assets\Wide310x150Logo.scale-200.png
    To run your app on UWP:
        react-native run-windows

执行react-native run-windows失败了，提示
    Build failed with message Error: Must have a minimum Windows SDK version 10.0.10586.0 installed. Check your build configuration.

### 安装运行需要的组件
Make sure you have installed all [requirements](https://github.com/Microsoft/react-native-windows#system-requirements) for React Native Windows. 

- You can build and deploy React Native Windows apps on the Pro or Enterprise versions of Windows 7 SP1, Windows 8.1, or Windows 10

  - You cannot run the emulators and some other developer tooling on the "Starter" or "Home" versions of these operating systems
  - You can run React Native Windows UWP apps only on Windows 10 devices, but React Native Windows WPF apps will run on Windows 7-10 so long as .NET 4.6 is installed on the end user's machine

- Download

  Visual Studio 2017 Community or Greater

  . (Visual Studio 2015 support has been deprecated.)

  - You will need to start Visual Studio after it is installed to do some final setup before it can be used to build or run your React Native Windows application

- [Windows 10 SDK Build 14393](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)

*Note*: Development on React Native Windows itself currently requires Visual Studio 2017. It is not supported with VS Code, but we will gladly accept pull requests to enable a great developer experience in those environments.

## Running a React Native Windows App
### With Visual Studio
### Without Visual Studio
In your React Native Windows project directory, run:

	react-native run-windows
A new Command Prompt window will open with the React packager as well as a React Native Windows app. You can now start developing! 🎉
​	
​	
