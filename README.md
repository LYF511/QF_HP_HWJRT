# 免责声明

## 此仓库为 OSHWHUB 开源项目 [物联网加热台](https://oshwhub.com/dhx233/pcb-heng-wen-jia-re-tai) [加热台量产计划](https://oshwhub.com/sheep_finder/pcb-heng-wen-jia-re-tai) 的 **第三方** 改版 相关代码及资料由 启凡科创 sheep_finder(找羊) 所有

## 仅供广大爱好者进行 DIY 使用！ **此项目禁止任何人以任何用途进行盈利 违者必究！**

## 因项目涉及到使用市电，调试和使用过程中一切触电事故概不负责，一经采用此开源项目将代表接受承担其存在的风险！

# 项目说明

此项目使用 Submodule, 克隆完仓库后还需执行

```
git submodule init
git submodule update
```

# 启凡科创 QF Maker

## QF HP桌面可调曲线多功能物联网加热台

硬件开源平台 [Link](https://oshwhub.com/dhx233/pcb-heng-wen-jia-re-tai)

找羊美化外观版本 [Link](https://oshwhub.com/sheep_finder/pcb-heng-wen-jia-re-tai)

最新更新维护：固件版本V1.62  2023-2-18  

每次详细说明都有更新，一定要朝下翻仔细阅读

## 维护日志

<details>
<summary>点击展开</summary>

<!-- <details> -->
<summary>V1.62</summary>

1. 合并找羊版本初号机风格固件

更新说明：

1. V1.61之前的版本更新会重置所有参数，需重新配置参数和物联网密匙
2. V1.61版本更新为增量更新，参数保留，但是有几率增量更新失败会导致参数将会被重置，如果当前您使用的是启凡科创默认UI风格且版本号为V1.61，可以不进行更新

<!-- </details> -->

<details>
<summary>V1.61</summary>

更新日志:

1. 修复V1.6的数据不能断电保存的BUG
2. 修复V1.6的物联网造成重启问题

</details>

<details>
<summary>V1.6</summary>

更新日志:

1. 新增风扇自动控制功能，默认开启，其会在停止加热后自动开启辅助降温，温度降低后自动关闭
2. 新增恢复出厂设置功能，如某些设置数据丢失或损坏后，可通过此功能重置加热台
3. 修复OLED库有几率造成重启的BUG
4. 修复IOT控制开启/关闭加热不上报状态的问题（仅开启/关闭上报，其他功能照旧不上报）
5. 修复开机后进菜单滚动会先朝上滚动一次的BUG
6. 优化操作，一些场景下单击也可确认、返回
7. 优化OLED库，动画显示更加丝滑
8. 优化一些菜单图标和选项的位置
9. 优化数据结构，二创作者可以方便轻松的添加用户数据
10. 更改使用说明内容

</details>

<details>
<summary>2022-5-2</summary>

1. 调整温度校准功能说明，理解更方便。
2. 改进CPU工作频率机制，强制工作于最高频率实现流畅动画。
3. 修复回流参数第三项温度超过255°会造成二次上电数据错误的bug，并将上限设置为自定义的实际温度。
4. 更改回流焊保温区温度下限130°到110°。
5. 资料包新增固件下载工具和最新固件V1.5，直接下载即可，同时资料包附带CH340系列串口转TTL驱动。
6. 加入回流焊模式时的温度调整提醒。
7. 开放回流焊加热开启温度下限为回流参数设定的保温段温度。
8. 彻底解决部分友友的Blinker连网问题，所有人都能开开心心接入物联网。
9. 资料包内带不常见的编码器（方向反的）编译好的固件可供选择，同时资料包包含配网教程视频。

</details>

<details>
<summary>2022-2-14</summary>

祝大家情人节快乐，送给大家一套实用的大更新！

1. 新增温度校准功能，彻底解决因大家购买的模块和元件误差参数不一导致的高温段温度误差问题！
2. 配网更改为WEB配网，解决部分手机机型智能配网无法扫描到设备的问题！
3. 优化编码器纠错算法，告别丢码和错码！
4. 优化低于38度时的升温速度，速度提升一倍！
5. 加大低温段（<200°）时的积分项，稳态误差纠正能力提升，但可能造成PTC内部核心略微（1-2°）的过冲！

</details>

<details>
<summary>2021-10-12</summary>

调整：

1. 更加激进的高温区段PID
2. 回流参数调整：预热区的最低值降低到130，回流区最高值提升到260（但是那么短时间应该到不了，仅仅为了加热更快）。

</details>

<details>
<summary>2021-10-4</summary>

新增：

1. LM358失调电压导致的温度误差补偿
2. 菜单加入配网说明
3. IOT新增风扇控制按钮 按一下翻转当前开启/关闭状态

</details>

<details>
<summary>2021-9-29</summary>

bug修复：

1. 修复了模式选择设置字体没居中的问题
2. 修复了加热状态下温度低于38度也会息屏的问题
3. 修复了回流焊百分比只能显示到95的问题

一些改动：

1. 回流焊进度百分比优化，消除数字大幅度跳动
2. 自动息屏时间延长为60s Tick_IRQ.h中可进行更改
3. 增加息屏和亮屏界面进入移除动画

</details>

<details>
<summary>2021-9-28</summary>

完成固件优化，现已完全上传资料

一些改动：

1. 最高温度限制到250℃
2. 增加温度降低后30S内无操作自动关闭屏幕减少屏幕损耗
3. 资料包中添加动态BOM单，但仍需看着原理图详细说明认真核对！

</details>

<details>
<summary>2021-9-26</summary>

硬件完成，软件界面系统已经完成  正在进行最后的参数调整   待完成后会进行同步更新   目前的固件仅开放主界面下单击编码器开启或关闭加热（温度270.    固件所有菜单开放体验（除了加热闭环功能其余都可以正常体验）

</details>

</details>

---

<!-- 吐槽一下，平台现在不能贴其他平台的链接 -->

演示、组装等视频均在B站，ID:[你也是他人的光呀](https://space.bilibili.com/341509721)

**此项目禁止任何人以任何手段进行牟利   违者必究**

有BUG请到交流群反馈(QQ)

官方交流一群：216066270（目前人已满，请加二群）

官方交流一群：704518455

**因项目涉及到使用市电，调试和使用过程中一切触电事故概不负责，一经采用此开源项目将代表接受承担其存在的风险！**

## 重要说明

一些重要说明，请仔细阅读：

0. 配网时不要插数据线，需要单独使用市电供电，否则有可能出现无限重启现象
1. NTC必须按照要求固定好，否则出现温度偏差大、抖动大、超调多的情况
2. 小爱控制是需要用到手机的功能：小爱训练计划自己添加指令的，不添加只能APP控制
3. 如果使用途中有奇奇怪怪的bug，可以恢复出厂设置试试
4. 配网的WIFI不要有特殊符号、中文、空格等奇奇怪怪的字符，且必须要是2.4G频段的
5. 编码器一定要停留在空档位置！不然会开不了机！这是ESP8266的硬件特性决定了的，程序并不能解决此问题

## 功能

0. 恒温加热模式和回流焊模式自由切换
1. 可视化自定义回流焊曲线
2. 回流焊过程中全程进度百分比显示
3. 可设置0-520分钟定时恒温时长，温度达到预设值后会显示倒计时
4. 物联网远程设置温度、模式、开关，可接入小爱自行训练命令，具体命令对应功能在MIOT.h中有说明
5. 预留DC5V风扇接口  自行控制是否开启风扇   方便用户拓展   也可设置为全自动控制在停止加热后会自动开启降温
6. 一体化功率控制部分   无须外接开关电源   方便携带   省桌面空间
7. 屏幕256级亮度可调整
8. 无操作低温下60S自动休眠
9. 硬件固有误差温度软件校准功能

## 特色

1. 单编码器操作   告别多按钮体验较差的操作
2. 依然延续QF Maker的流畅全局动画
3. 集成自动下载电路，不需要弄懂下载模式等，傻瓜式插入数据线即可一键下载程序，后续固件版本更新亦能轻松更新
4. 整体采用便宜的方案  适合低预算又想用回流焊的人群（具体价格自己拿着资料算  我不是计算机）
5. 加热尺寸68*70MM  满足大部分嵌入式弱电板子  如需更大尺寸的自行修改   不会改的移步辉神的开源项目或采用其他二创的大版本开源项目

## 配置物联网步骤

1. Blinker的APP里面注册一个独立设备（步骤我B站有视频教程，只需要看注册Blinker设备那里就行，ESP Touch配网为V1.3及以下版本固件的配网方式），复制注册的密匙在加热台设置里进行WEB配置即可。
2. 打开资料包中的 “基础手机端控制界面参数.txt"将代码全选复制到Blinker对应的设备的界面配置下输入保存刷新一下即可
3. 注意：Wifi网络必须为能连接外网且无需认证的网络（校园网之类的需要认证的不行）

## 温度校准步骤

ps：编码器单击选中和取消选中选项，未选中下转动编码器切换选项

1. 如果有准确的测温仪器能测量到设备内部PTC温度，可以自行测量后更改选项内的实测最高温度值。没仪器的同学就默认的255就好
2. 切换到偏差最高选项，单击进入自动校准程序，校准完毕后程序将自动退出，中途可单击返回终止校准。（自动校准功能需要在未开启加热且加热板温度低于150时才能启用）

## 附

一些元件的实物图在附件资料包里，自行下载资料包看  不要上来就问

3D模型防触电围栏普通材料就行，不用耐高温！建议一定要装，谁也不能保证会不会倒霉触电，加了围栏捧着都不会有问题

铜柱尺寸推荐：

- M3*25+6  X4 (主控与中间隔热板连接）
- M3*10+6  X8( 两层隔热板、加热板之间连接）
- M3*6+6  X4 (主控板与底板之间的连接）
- 沉头M3螺丝 * 12
- M3螺母 * 24 

详细元件购买说明移步原理图上自己看
