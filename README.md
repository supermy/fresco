# Fresco 

Fresco是Facebook最新推出的一款用于Android应用中展示图片的强大图片库，可以从网络、本地存储和本地资源中加载图片。其中的Drawees可以显示占位符，直到图片加载完成。而当图片从屏幕上消失时，会自动释放内存。

主要特性：

内存
解压后的图片和Android的位图都会占据很大的内存，这导致Java 垃圾收集器更频繁的运行，也让应用变得更加缓慢，这一问题在没有对垃圾收集器进行完善的Android 5.0上尤为严重。

在Android 4.x及以下版本，Fresco将图片放置在Android内存的一个特殊位置。这可以确保当图像不在屏幕上显示时，可以自动释放它们所占的内存。让应用运行的更快速，且不易崩溃。

使用Fresco的应用，即使在配置低端的设备上也能正常运行，而且你无需经常性地去担心图片的内存占用情况。

Streaming
Web上的渐进式（Progressive）JPEG图片已经存在多年，打开文件过程中，会先显示整个图片的模糊轮廓，随着扫描次数的增加，图片变得越来越清晰。这种格式可以说是网络较慢情况下的救星，通过图片的轮廓知道正在加载的图片大概是什么。

Android自己的图片库不支持streaming，而Fresco可以，只需指定一个URI，你的应用程序就可以随着数据的到来，自动更新它的显示。

动画
动画GIF和WebP应该是应用的难点，每一帧都是一个大型的位图，而每个动画都是一系列的帧。Fresco则负责加载和处理这些帧及管理它们的内存。

Drawing

Fresco在显示方面使用了Drawees，Fresco的Drawees能够显示占位符，直到图片已加载，并自动显示到图像到达时：

将图片扩展至自定义的焦点，而不是作为处理的中心。
使用圆角化或圆形来显示图像。
如果网络加载失败的话，用户可以点击占位符重新加载图像。
显示自定义背景、浮窗小部件（overlays）或图像上的进度条。
当用户点击图片，自定义浮窗小部件。
加载
Fresco的图像管道可以让你以多种方法来自定义加载：

为一个图像指定不同的URI，从中选取一个已经缓存的显示。
优先显示低分辨率图像，待数据到达后交换到高的分辨率。
如果图像有EXIF缩略图，首先显示缩略图，直到整个图片被加载出来（只针对本地图片）。
调整或旋转图像。
即使是在老版的Android上也可以解码WebP图像，只不过不是全部支持。


Fresco is a powerful system for displaying images in Android applications.

Fresco takes care of image loading and display, so you don't have to. It will load images from the network, local storage, or local resources, and display a placeholder until the image has arrived. It has two levels of cache; one in memory and another in internal storage.

In Android 4.x and lower, Fresco puts images in a special region of Android memory. This lets your application run faster - and suffer the dreaded `OutOfMemoryError` much less often.

Fresco also supports:

* streaming of progressive JPEGs
* display of animated GIFs and WebPs
* extensive customization of image loading and display
* and many more!

Find out more at our [website](http://frescolib.org/index.html).

## Requirements

Fresco can be included in any Android application. 

Fresco supports Android 2.3 (Gingerbread) and later. 

## Using Fresco in your application

If you are building with Gradle, simply add the following line to the `dependencies` section of your `build.gradle` file:

```groovy
compile 'com.facebook.fresco:fresco:0.1.0+'
```

See our [download](http://frescolib.org/docs/download-fresco.html) page for other options.

<div style="text-align: center; box-sizing: border-box; line-height: 22px; color: #444; font-family:proxima-nova, 'Helvetica Neue', Helvetica, Arial, sans-serif">
<a style="background: #cc2e39; font-weight: bold; color: #ffffff; text-transform: uppercase; padding: 10px 20px; display: inline-block; margin: 1em; box-shadow: 0px 1px 2px rgba(0,0,0,0.3); text-decoration:none" href="http://frescolib.org/docs/index.html">Get Started</a>
</div>

## Building Fresco from source

Install the Android [SDK](https://developer.android.com/sdk/index.html#Other) if you haven't already. Then run the Android SDK Manager and install the Android Support Library and Android Support Repository.

Download the Android [NDK](https://developer.android.com/tools/sdk/ndk/index.html). Then add the directory containing it to your PATH environment variable.

Then just do

```sh
git clone https://github.com/facebook/fresco.git
cd fresco
./gradlew build
```

## Join the Fresco community

Please use our [issues page](https://github.com/facebook/fresco/issues) to let us know of any problems.

For pull requests, please see the [CONTRIBUTING](https://github.com/facebook/fresco/blob/master/CONTRIBUTING.md) file for information on how to help out.

## License
Fresco is [BSD-licensed](https://github.com/facebook/fresco/blob/master/LICENSE). We also provide an additional [patent grant](https://github.com/facebook/fresco/blob/master/PATENTS).
