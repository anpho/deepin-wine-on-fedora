# deepin-wine-on-fedora
在Fedora上安装Deepin-Wine最新版的方法


## TL；DR

打开 [Fedora App分享空间](http://v21cesc.ys168.com) 下载相应的rpm包，然后一通操作：
```
sudo dnf install *.rpm
```
就完成了

对于TIM／QQ的中文显示为方块的问题，一通操作：
```
WINEPREFIX=~/.deepinwine/Deepin-QQ/ winetricks fakechinese
WINEPREFIX=~/.deepinwine/Deepin-TIM/ winetricks fakechinese
```

以上在Fedora33平台测试成功。

## Why Deepin-Wine?

当然是因为原版的wine在面对一些花哨的windows程序时存在一系列的兼容性问题啊，比如应用程序四周的阴影会一直出现在桌面上（无视z-index），比如各种闪退等等。Deepin-Wine提供了一种hack过的解决方案，可以方便地安装微信（目前版本3.0）、QQ、TIM等

## How to use?

打开网页 [Fedora App分享空间](http://v21cesc.ys168.com/)，下载以下项目：

1. [deepin-wine-all-in-one-1.0-1.x86_64.rpm](http://ys-d.ys168.com/616028054/k732M4K2G9JNGMjfgXVL/deepin-wine-all-in-one-1.0-1.x86_64.rpm)
2. 其他你需要装的东西

把所有下载的rpm放到一个文件夹内，打开终端，执行：
```
sudo dnf install *.rpm
```
DNF会自动分析信赖，然后按顺序安装进去。装完后记得安装winetricks，一般来说是```sudo dnf install winetricks.noarch```，建议使用tab键自动补全。

## QQ/TIM文字变方框？

字体不全的问题，上面TL；DR部分有说明，用winetricks安装个fakechinese就行了。当然如果你网速快也可以试试cjkfonts……

## 迅雷无法使用？

我也不知道原因，看起来安装完以后目录是空的，可能是RPM打包有问题。
