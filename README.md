# testIpa



[在 iPhone Safari 点击下载 ipa](itms-services://?action=download-manifest&url=https://raw.githubusercontent.com/poos/testIpa/master/manifest.plist)

---

博客文章的配套代码：

[局域网/公网 发布ipa （类似蒲公英，fir 等）](https://poos.github.io/2018/10/30/ProjectIpaTest/)

借用 github存储 manifest.plist; Build/xx.app 脚本导出 ipa; 借用博客在局域网发布...

---

下面是部分博客内容

---
---



## 踩坑点

10月30日

1. **plist 要在 https:// 上面**

2. **plist 中的链接要准确获取：ipa为下载链接，image同样，bundle-identifier要准确，bundle-version和title可以不准确**

3. **ipa 下载地址选择：优先选择局域网；github上传大文件使用Git Lfs（不推荐下载慢）；七牛下载（未正确获取下载链接，未测试）**

4. **导出 ipa 方式选择：xcrun + PackageApplication（在日常 build 中导出ipa）；脚本打包 achieve，导出出 ipa**

```
xcrun -sdk iphoneos PackageApplication -v ~/xx/xx.app -o ~/xx/xx.ipa
```

5. **在局域网网页发布：使用 xxx.loacl:4000/ 网址；个人借用了博客 jekyll 新建了个发布静态网页**

```
jekyll serve -w --host=0.0.0.0

http://xx.local:4000/test/app
```

...

## 原理和分析

iOS 的 ipa 可以通过链接（ex：itms-services://?action=download-manifest&url=https://xxx/xx.plist）去请求 itunes 安装app（没有静态网页直接请求这个链接，或者生成二维码在相机扫码即可下载 ipa）。

plist 文件格式如下： 有两个对象一个存储 ipa 和图片，另一个对象存储 app identifier 和 版本信息，plist 代码稍后在下边列出。

...


## 过程

### github 发布ipa

...

### github 上传ipa

...

###  打包 ipa 的 N 种方式

...

#### Xcrun

...

### mainfest 生成

...

### ipa 下载

...

#### jekyll 静态博客发布到局域网

...


