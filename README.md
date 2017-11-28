<font color = "#2367c9" size = "5" >一，前言：</font>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;学习react-native相信对于我们最好的教程就是官方教程。因此学习和查看官方demo。是我们学习进步的阶梯。本文是博主学习react-native中遇到的一些基本问题，分享出来供大家学习和参考：

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;转载请注明出处：<font color = "#D2691E">http://blog.csdn.net/u013233097/article/details/78362760</font>   如果对你有用，欢迎fork或者star。或者点赞关注以及评论。

<font color = "#2367c9" size = "5" >二，准备工作：</font>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;官方UIExplorer demo 是需要我们配置环境才能运行的。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#f00">准备工作：npm , node, git 具体安装法方式看我前几篇文章。</font>

<font color = "#2367c9" size = "5" >三，Action 开始行动：</font>

1,打开  gitbash ， 执行命令：

```
 git clone https://github.com/facebook/react-native.git
```

![执行命令](http://img.blog.csdn.net/20171128165512244?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

clone 成功后  react-native 内容：

![内容](http://img.blog.csdn.net/20171128165610573?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

2, 打开自带的 示例包 ：

<font color="#f00" size="2">注意： rn 各个版本示例包名不一样，有的是在  examples文件夹下，有的是在 RnTester下：</font>

找到  示例包 ：

![这里写图片描述](http://img.blog.csdn.net/20171128170117040?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

3， 打开README.md 说明文件：

查看提示：

```
//  以运行  Android app 为例：
## Running this app

Before running the app, make sure you ran:

    git clone https://github.com/facebook/react-native.git
    cd react-native
    npm install
```
根据提示执行命令：

![这里写图片描述](http://img.blog.csdn.net/20171128170401820?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

4， 继续查看文档：

```
### Running on Android

You'll need to have all the [prerequisites](https://github.com/facebook/react-native/tree/master/ReactAndroid#prerequisites) (SDK, NDK) for Building React Native installed.

Start an Android emulator ([Genymotion](https://www.genymotion.com) is recommended).

    cd react-native
    ./gradlew :RNTester:android:app:installDebug
    ./scripts/packager.sh

_Note: Building for the first time can take a while._

Open the RNTester app in your emulator.

See [Running on Device](https://facebook.github.io/react-native/docs/running-on-device.html) in case you want to use a physical device.
```

继续根据文档提示   输入命令：

```
 ./gradlew :RNTester:android:app:installDebug
```

发现报错， 下载boost 失败：

![这里写图片描述](http://img.blog.csdn.net/20171128171003986?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
:ReactAndroid:downloadBoost
Invalid cookie header: "Set-Cookie: logged_in=no; domain=.github.com; path=/; expires=Sat, 28 Nov 2037 09:05:12 -0000; secure; HttpOnly". Invalid 'expires' attribute: Sat, 28 Nov 2037 09:05:12 -0000
:ReactAndroid:downloadBoost FAILED
```

从网上找到对应版本（一般错误信息会提示），粘贴复制进：ReactAndroid- build-downloads  文件夹下：

![这里写图片描述](http://img.blog.csdn.net/20171128170922944?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)


5，继续执行命令：

```
./gradlew :RNTester:android:app:installDebug
```
 安装成功：

可以看到  我们模拟器上已经被安装了RnTester:

![这里写图片描述](http://img.blog.csdn.net/20171128173403314?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

6，启动服务命令：

```
./scripts/packager.sh
```

开启成功：
![这里写图片描述](http://img.blog.csdn.net/20171128173816799?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)


打开 我们的App    RNTester 运行成功：

![这里写图片描述](http://img.blog.csdn.net/20171128173625400?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzIzMzA5Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

官方Demo.  仅供学习。




需要资源者： 异步github：






<font color="#f00">下载   错误信息提示：</font>

1.Error:Execution failed for task ':ReactAndroid:downloadBoost'. 
> java.io.FileNotFoundException: http://nchc.dl.sourceforge.net/project/boost/boost/1.57.0/boost_1_57_0.zip
手动下载boost_1_57_0.zip 复制到/node_modules/react-native/ReactAndroid/build/downloads目录下,下载不了请使用vpn。

2.Error:Execution failed for task ':ReactAndroid:downloadJSCHeaders'. 
> java.net.UnknownHostException: svn.webkit.org 
到https://svn.webkit.org/repository/webkit/!svn/bc/174650/trunk/Source/JavaScriptCore/API/ 下载['JavaScript.h', 'JSBase.h', 'JSContextRef.h', 'JSObjectRef.h', 'JSRetainPtr.h', 'JSStringRef.h', 'JSValueRef.h', 'WebKitAvailability.h']
复制到/node_modules/react-native/ReactAndroid/build/downloads/jsc目录下。

3.Error:Execution failed for task ':ReactAndroid:buildReactNdkLib'. 
> Process 'command '/Users/shixiang/Library/Android/android-ndk-r11b/ndk-build'' finished with non-zero exit value 2
这个是我遇到的ndk版本问题,使用android-ndk-r10e后正常。
