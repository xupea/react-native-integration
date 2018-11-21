# react-native-integration

准备环境:
macOS High Sierra - 10.13.6
Android Studio 3.2.1
react-native-cli: 2.0.1

Step1:

Android Studio 创建 新工程

Step2:

com.android.support:appcompat-v7 默认已经被添加, 所以只需在Module:app添加 
```
implementation "com.facebook.react:react-native:+"
```
到dependencies

运行错误1:

```
E/SoLoader: Error when loading lib: dlopen failed: "/data/data/com.example.chuangkegongchang.demointegration/lib-main/libgnustl_shared.so" is 32-bit instead of 64-bit lib hash: 38099cfdfc816f823cb69c5387381ddd search path is /data/app/com.example.chuangkegongchang.demointegration-Qv4Co1b7yJGsFGosdVTfow==/lib/x86_64
    couldn't find DSO to load: libgnustl_shared.so caused by: dlopen failed: "/data/data/com.example.chuangkegongchang.demointegration/lib-main/libgnustl_shared.so" is 32-bit instead of 64-bit
    couldn't find DSO to load: libglog.so caused by: couldn't find DSO to load: libgnustl_shared.so caused by: dlopen failed: "/data/data/com.example.chuangkegongchang.demointegration/lib-main/libgnustl_shared.so" is 32-bit instead of 64-bit
    couldn't find DSO to load: libglog_init.so caused by: couldn't find DSO to load: libglog.so caused by: couldn't find DSO to load: libgnustl_shared.so caused by: dlopen failed: "/data/data/com.example.chuangkegongchang.demointegration/lib-main/libgnustl_shared.so" is 32-bit instead of 64-bit
    couldn't find DSO to load: libreactnativejni.so caused by: couldn't find DSO to load: libglog_init.so caused by: couldn't find DSO to load: libglog.so caused by: couldn't find DSO to load: libgnustl_shared.so caused by: dlopen failed: "/data/data/com.example.chuangkegongchang.demointegration/lib-main/libgnustl_shared.so" is 32-bit instead of 64-bit
E/AndroidRuntime: FATAL EXCEPTION: Thread-4
    Process: com.example.chuangkegongchang.demointegration, PID: 10560
    java.lang.UnsatisfiedLinkError: couldn't find DSO to load: libreactnativejni.so caused by: couldn't find DSO to load: libglog_init.so caused by: couldn't find DSO to load: libglog.so caused by: couldn't find DSO to load: libgnustl_shared.so caused by: dlopen failed: "/data/data/com.example.chuangkegongchang.demointegration/lib-main/libgnustl_shared.so" is 32-bit instead of 64-bit
        at com.facebook.soloader.SoLoader.doLoadLibraryBySoName(SoLoader.java:703)
        at com.facebook.soloader.SoLoader.loadLibraryBySoName(SoLoader.java:564)
        at com.facebook.soloader.SoLoader.loadLibrary(SoLoader.java:500)
        at com.facebook.soloader.SoLoader.loadLibrary(SoLoader.java:455)
        at com.facebook.react.bridge.ReactBridge.staticInit(ReactBridge.java:18)
        at com.facebook.react.bridge.NativeMap.<clinit>(NativeMap.java:19)
        at com.facebook.react.bridge.JSCJavaScriptExecutorFactory.create(JSCJavaScriptExecutorFactory.java:21)
        at com.facebook.react.ReactInstanceManager$5.run(ReactInstanceManager.java:917)
        at java.lang.Thread.run(Thread.java:764)
I/Process: Sending signal. PID: 10560 SIG: 9
Application terminated.
```
解决方案:
https://blog.csdn.net/chichengjunma/article/details/53815299

运行错误2:

```
Unable to load script from assets 'index.android.bundle'. Make sure your bundle is packaged correctly or you're running a packager server
```

解决方案:

https://stackoverflow.com/questions/45940861/android-8-cleartext-http-traffic-not-permitted/50834600#50834600

参考资料:

https://github.com/Shelomi/RNIntegration

