## 以下为macOS安装配置react native环境的教程

### 安装最新版的nodejs,npm,cnpm

###安装 Android
	如果想要编写 React Native 安卓应用程序， 您需要安装安卓 SDK （如果您不想在真机上运行您的应用程序，那么您还需要一个安卓模拟器）。

### 快速开始
```
	$ npm install -g react-native-cli
	$ react-native init AwesomeProject
	$ cd AwesomeProject/

```

####运行 Android 应用程序：
	* ` $ react-native run-android `
	* 在选定的文本编辑器中打开 ` index.android.js ` 并且编辑代码。
	* 按下菜单按钮 （默认情况下是 F2，或在 Genymotion 中点击 ⌘ M），然后选择 Reload JS 看看发生了什么变化！
	* 在一个终端中运行 ` adb logcat *:S ReactNative:V ReactNativeJS:V ` 来查看您的应用程序日志。

### 让安卓支持现有的 React Native 项目
	如果您现在已经拥有一个(iOS) React Native 项目并且想让安卓也支持它, 那么您需要在您现有的项目目录中执行以下命令：

	1.将您 ` package.json ` 文件中的 ` react-native `目录更新到` 最新的版本 `

1. ` $ npm install `
2. ` $ react-native android `