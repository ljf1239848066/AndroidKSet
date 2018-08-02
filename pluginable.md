# 插件化

## 插件化的功能

1. 插件化最早出现是因为65535问题出现的，用于查分多个dex并动态加载dex来防止65535问题

2. 现在很多公司用插件化来做模块的动态加载，这样既能实现web端一样的随时更新，还能减少apk包的体积，其实就是加载一个未安装的apk。

3. 热修复，热修复其实也是动态加载原理

4. 换肤，使用动态的资源加载可以实现换肤功能

5. 还可以通过hook系统的一些类做一些你想做的坏事。

## 插件化的原理


## 常见插件化框架介绍

### 阿里——[andfix](https://github.com/alibaba/AndFix)

### 腾讯——[thinker](https://github.com/Tencent/tinker)

### 滴滴——[VirtualAPK](https://github.com/didi/VirtualAPK)

### 360——[DroidPlugin](https://github.com/Qihoo360/DroidPlugin)

### 任玉刚——[dynamic-load-apk](https://github.com/singwhatiwanna/dynamic-load-apk)