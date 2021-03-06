# 概念梳理
首先说明, 目前 本人系统是 `Windows 10 build 10586 最新版`.  
模拟器 最好 不要 同时安装 多个, 以前 `VirtualBox` 阵营的 老是 相互冲突.  
不过 现在 好多了, 因为大家都自己 集成 自己修改过的 `VirtualBox`.  
注意 如果 CPU 支持 `VT-x(虚拟化)技术`, 请务必开启, 性能翻倍.

模拟器 主要的 几大核心: 
  1. Microsoft
  2. KVM/QUME
  3. Android-x86
  4. 其他(我可能 没有弄清楚的, 暂时都 归到 这里面)


# Microsoft 阵营
#### Visual Studio Android Emulator ([官网][VS Android Emulator])
[VS Android Emulator]: https://www.visualstudio.com/en-us/explore/msft-android-emulator-vs.aspx
[1]: https://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/debug-on-emulator/#Emulator_Choices)
前身是 `Xamarin Android Player`, 不过已经被废弃了,  
自从 `Xamarin` 被微软收购 并开源, 参看 [官方说明][1].  
没用过, 因为 要求 开启 `Hyper-V` 机制.  
这个 目前 这个功能 跟 `VitualBox` 是冲突的.  
不知道 微软 具体 怎么实现的, 暂且 把他 自己归到一类 (毕竟国际良心大厂)...


# KVM/QUME 阵营
#### Google AVD/Intel HAXM ([AVD 官网][Google AVD], [HAXM 官网][Intel HAXM])
[Google AVD]: https://developer.android.com/studio/run/managing-avds.html
[Intel HAXM]: https://software.intel.com/en-us/android/articles/intel-hardware-accelerated-execution-manager
AVD 1.0 最初是 SDK 自带的 模拟器, 一开始 非常的卡.  
于是乎 `Intel` 自己弄了一个 `x86 架构`的 `HAXM`,  
旨在通过 `Hyper-V` 提升`宿主(Windows)` `x86 指令集`上的 速度.  
后来 又有了 `AVD 2.0` + `Android Studio 2.0`,  
性能确实 提升了不少, 功能 也丰富了很多.  
最大的好处 就是, 版本多, 超原生, 方便 代码调试.


# Android-x86 阵营
#### Android-x86 (http://www.android-x86.org/)
屌得不行了, 跟 `VirtualBox` 配合用 已经逆天.  
这个阵营里面的 模拟器 大多是 跟他 有 藕断丝连 的关系.  
此外 还有 有很多 衍生版本, 例如 `RemixOS` 等.  
目前正在 研发 `5.1.x`, 相当期待.  
缺点就是 就是 安装 需要 用户 自己折腾一下 (对于开发者 这算优点吧).


#### BlueStacks (http://www.bluestacks.com/)
很多游戏玩家 最初接触的 游戏模拟器 吧,  
`BlueStacks 1` 直接用来 做 开发模拟器 感觉体验很差.  
`BlueStacks 1` 稳定性不错, 稍微有点慢.  
`BlueStacks 2` 是目前最新版本. 体验 依旧 不太好.  
关键是 不能直接 配置 `分辨率` 和 `DPI`, 哎, 开发者 卸载卸载.


#### 靠谱助手 (http://www.kpzs.com/)
最早用的 毒瘤之一, 镜像很多,  
因为 内嵌了 修改过的 `BlueStacks` 和 `天天模拟器`.  
后来放弃了, 毕竟 `BlueStacks`...


#### 天天模拟器 (http://www.ttmnq.com/)
一开始很不错的 游戏模拟器, 跑分很高.  
目前也支持 自动 `adb` 了.  目前还在 `4.4.4`.  
最近出了 `MacOS` 版本, 持续关注中.


#### 逍遥模拟器 (http://www.xyaz.cn/)
这是我 今年才开始用的 新兴模拟器.  
`Windows 端` 偶尔闪退, 假死.  
`Android` 有时候 也会有 bug, 比如说 状态栏 不能拉下来.  
目前有 `4.2.2(稳定)` 和 `5.1.1(公测)` `两个 Android 核心`.  
我 两个版本 同时在用了, 感觉还算是可以的.  
不过 目前 最新版 好像不太稳定啊,  
公司的 `Win7` 能启动(不能用官网教程 覆盖安装, 需要 手动解压覆盖),  
但是 这台 `Win10` 死活卡在 100% 不动弹...


#### 夜神模拟器 (http://www.yeshen.com/)
还可以吧, 感觉 `Android 层面` 不是很流畅.  
虽然是 后起的, `4.4.2`, 但是 感觉用不习惯...  
跟 逍遥模拟器 一样, 也开始搞 `5.1.1(内测)` 了.  
最新稳定版 好像 也不太稳定, 莫名其妙 就会卡屏...


#### Droid4X(海马玩) (http://www.droid4x.com/)
前几年 一直用的, 后来不用了, 一直在 `4.2.2`,  
感觉 单纯用来 玩游戏还是可以的.  
做的挺大的, 都打入 海外市场了, 有一段时间 没用了.  
但是 `0.10 版本` 的自带 启动器 实在是太恶心了, 用来调试 伤不起.  
装一个 第三方 启动器还可以吧... 还是挺流畅的.
不过 这 坑爹软件 回给你装一个 `VisualBox 4.3.12_zzzz`, 
直接破坏 现有的 `VirtualBox` 开发环境. 垃圾, 卸载卸载.


#### DuOS (http://www.amiduos.com/)
这个模拟器 我也是今天才知道的, 居然也是 国人制作(大雾).  
官网 上 有一堆 调试工具, 但是 不太喜欢..  
因为 不能 自定义安装, 我的固态硬盘啊!!  
不能 窗口化, 只能最大化, 最小化; 莫名闪退两次;  
冷启动 超级迟钝, 马蛋 还收费, 安装 被杀软拦截了两次.  
哎, 垃圾软件, 毁我流量, 卸载卸载!!


#### Genymotion (https://www.genymotion.com/)
虽然 这个模拟器 是为开发者 准备的, 但是 毕竟也是 收费的.  
他钻了 `AVD 1.0` 不强大的空子, 大肆宣传.  
类似于 `CyanogenMod` 钻了 `Google` 的 `Nexus` 空子...  
其实 这个 模拟器 并不流畅, 也很卡, 而且经常被墙...  
唯一好处就是 模拟器 比较接近 仿真器,  
与真机 参数 "接近" (汗 其实也是模拟的).  
和 开发工具 结合地 比较紧密 (拉倒吧, 就是 工具栏 多了一个 快捷按钮 而已).   
跟 `AVD` 一样, 设备比较多, 需要 联网下载.  
一般般吧, 目前来看, 无功无过.


# 其他 阵营
#### Andy (http://www.andyroid.net/)
一个 经常被墙的模拟器, 平平庸庸 的.  
不太喜欢, 默认钻 C盘. 我的固态啊!  
核心 `4.2.2` (`4.2.2`/`4.4.2`/`4.4.4` 统治世界 =_ =).  
参数可控, 都在 通知区域 托盘的 右键菜单 里面...  
反正我是不喜欢用, 卸载.


#### Windroye(文卓爷)/Windroy(极客版) (http://www.windroye.com/)
文卓爷 还不错吧, 居然下载地址 只有 网盘分流..  
用过很多次, 目前在 `4.4.2` 版本. 
一般般吧, 大众脸, 不太喜欢, 默认钻 C盘.  
模拟器 镜像文件 存放路径 安装的时候 可以指定.  
参数可以自己定制, 不如 其他模拟器 名声大.  

相比之下 极客版 就差很多很多, 虽然体积很小.  
最关键是 极客版 经常循环闪退...  
还有 就是 跟 `DuOS` 一样, 不能够窗口化, 不能够 配置 `分辨率` 和 `DPI`.  
也是醉了, 卸载 极客版!


#### 还有很多山寨 夹缝中求生存 的, 毕竟 竞争很激烈:
(**2016-11-06 补充**) 新模拟器  
http://dl.pconline.com.cn/sort/1872.html

#### 一般般
- 多玩模拟器 http://www.dwmoniqi.com/index.html
- iTools 模拟器 http://pro.itools.cn/simulate/
- iTools 模拟器 http://pro.itools.cn/syzs/

#### =_ =, 玩游戏 确实可以...
- 腾讯手游助手 http://guanjia.qq.com/product/gameassitant/

#### 功能太弱, 比如说定位失败
- 网易MuMu http://mumu.163.com/
- 51模拟器 http://www.51mnq.com/

#### 压根没有定位功能
- 侠客模拟器 http://www.xiakeshouyou.com/
- 手游岛 http://www.shouyoudao.com/
- PKBox http://www.pkbox.cn/
- 叶子猪 http://tools.yzz.cn/
- 携玩助手 http://www.xiewan.org/
- 新浪手游助手 http://www.987you.com/
- 小皮助手 http://pc.xiaopi.com/

#### 反复安装失败, 不支持 armeabi?
- 猩猩安卓模拟器 http://www.xxzs.tv/xxmnq

#### 用了 海马玩 镜像 (剽窃?)
- 星光助手 http://www.17xgzs.com/

#### 靠谱助手/蓝栈 换个壳...
- 超神助手 http://www.kpzs.com/topic/cszsbaidu/
- 东东助手 http://www.idongdong.com/zs/
- 蓝光手游大师 http://blue.17huang.com/
- 安卓模拟器大师 http://www.azmaster.cn/
- 说玩模拟器 http://pc.shuowan.com/

# 2016-08-26 补充
`AVD`/`Genymotion` 的 `x86` 不能兼容 纯 `arm` 应用.  
但是 国内的 模拟器 就是可以强行运行的.
https://github.com/imknown/IMKDevelopmentDaily/blob/master/2016/08/25_%E6%A8%A1%E6%8B%9F%E5%99%A8%E3%80%81%E4%BB%BF%E7%9C%9F%E5%99%A8%E3%80%81%E8%99%9A%E6%8B%9F%E8%AE%BE%E5%A4%87%E5%92%8C%E8%99%9A%E6%8B%9F%E6%9C%BA%E7%9A%84%E5%8C%BA%E5%88%AB.md

# 推荐使用 (排名越靠前, 越被推荐)
  1. AVD/HAXM
  2. Genymotion
  3. 夜神模拟器
  4. 天天模拟器
  5. 逍遥模拟器

# 总结
再也不用 小众模拟器!!
