<I am Unicode File!>

TCP半开连接数破解全能完美补丁（修改内存方式，支持XP SP2 SP3/Vista SP1 SP2/Windows 7, 32/64位）

软件名称： TCP-Z  (TCP-Z Network Monitor)
操作系统： Windows XP/2003/2008/Vista/Windows 7, All SP*, All 32bit (x86) / 64bit (x64)
作者邮箱： deepxw#126.com
官方网站： http://deepxw.lingd.net
          http://deepxw.blogspot.com   (English)

破解TCP/IP连接数限制，释放网络潜能，下载更快，浏览更流畅。
图表显示网络连接数据，分析下载速度的好帮手。

特色：
1, 快捷安全： 修改内存中的半开连接数限制值，立即生效，无需重启。不修改系统文件Tcpip.sys，安全。

2，兼容性好： 特征码查找，TCP-Z认识所有Tcpip.sys，通杀所有带限制的Windows！

3, 专业图表： TCP-Z实时显示系统当前活动的TCP连接数、半开连接数、新建队列，以及上传、下载速度的历史曲线。每分钟统计更新TCP新建队列超限警告事件次数。

*************
*  使用说明  *
*************

1, 手动修改：使用图形界面程序。

2, 自动修改：安装虚拟驱动程序(VirtualDevice目录下)，只需要安装一次，傻瓜化全自动修改，无需人工干预。设备管理器属性页可以自定义上限数值。

两种方式可以独立运行，任选其中之一就可以了。

TCP-Z是修改内存方式。你如果想使用修改文件方式，请使用另一工具：通用Tcpip.sys文件补丁(Universal Tcpip.sys Patch)。


* 键盘快捷键
切换窗口页		Ctrl + Tab
切换控件			Tab
确认			Space
截取TCP-Z窗口为图片文件	F5
截取全屏窗口为图片文件	F6
 
* 命令行
tcpz.exe  -limit:200			修改新限制数至200。
tcpz.exe  -limit:200  -autoexit		修改新限制数至200，修改完成自动退出程序。
tcpz.exe  -minimize			运行时窗口最小化。


****************
* 常见问题及解决 *
****************
1, 图形界面程序，需要右键点Tcpz.exe，选择以管理员身份运行才能正常加载。

2, 64位Vista/Win7，需要允许测试数字签名。
右键点命令提示符，选择以管理员身份运行，输入:
bcdedit.exe -set loadoptions DDISABLE_INTEGRITY_CHECKS
bcdedit.exe -set TESTSIGNING ON
运行后要重启才生效，只需运行一次。
桌面显示“测试模式”字符串，可以使用virtualdevice目录下的RemoveWatermarkX64.exe去除，右键管理员运行。

32位系统，不需要这个设置！

3, 如果程序非正常关闭后，再次运行时提示加载驱动程序失败，你需要以管理员身份打开命令提示符运行命令：
32位：
REG DELETE HKLM\SYSTEM\CurrentControlSet\Services\tcpz-x86
64位
REG DELETE HKLM\SYSTEM\CurrentControlSet\Services\tcpz-x64
删除[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\Root\LEGACY_TCPZ-X86]项目。
然后重启，重新打开程序。

4, Windows XP支持内存补丁与文件补丁两种方式，二选一； Vista/Win7只支持内存补丁方式。

5，在64位Windows XP下使用文件补丁，需要使用64位的TCP-Z，否则无法禁用SFC而导致修改文件失败。

6, 软件在Windows 2003/2008也会显示一个连接数限制值，但服务器操作系统是忽略那个限制值的。

7, Vista/Windows 7可以使用TCP-Z虚拟驱动修改半开连接数上限为无限。数值0代表无限。

8, 如果TCP-Z图表中的特殊箭头标志，需要Wingdings 3字体的支持。如果不能显示，请安装这个字体。

9, GUI程序增加支持键盘操作。Ctrl+Tab＝切换标签页；Tab＝切换控件。


Keywords: Tcpip.sys, TCP/IP同时连接数,TCP/IP半开连接数,并发连接数,补丁,half open, evID 4226,patch,crack

//历史更新：
2008.09.12
  * 以原ASCII版的TCP-Z Network Monitor的技术为基础，全新制作了这款Unicode版的TCP-Z，繁体中文没问题了。
    相比以前版本，禁用了啰嗦的Vista文件补丁功能，其他主要功能没什么变化。
    界面变化比较大，更新图表控件，比前版本简洁清晰。
    程序变肥了。项目用VS2005编译，MFC采用静态连接，所以程序个头比较大。

2008.09.14
  + 添加英文/简体中文支持。

2008.09.21
  + 制作专属的安装程序，放弃Devon脚本安装方式。
  * 补丁驱动程序增加一次查找半开连接数限制地址的尝试，提高成功率。

2008.10.13
  + 添加读取Windows 7 M1的tcpip.sys文件限制数。

2008.10.23 V1.5.3.15
  + 从tcpip.sys读取、显示TCP新建队列数值。
  + Windows 7 M1内存补丁。
  * 少部分网卡无法读取显示速度。

2008.10.30  V1.5.5.20
  + 支持Windows 7 M3 32位内存补丁。
  + 添加AMD多核CPU的不安全提示。
  * 驱动程序加载的判断，由读取文件版本改为读取系统版本。

2008.11.01  V1.5.6.25
  + 支持Windows 7 M3 64位内存补丁。(Beta)
  * 修改Windows XP的文件限制数上限，从200放宽到1000。（虽然没什么必要）
  * 禁用NT5 SFC的方法，恢复为早期的方法。1.5系列中间用了一个简单的方法，现在发现不通用。

2008.11.07  V2.0.0.30 beta
  * 修改TCP-Z驱动程序中所有查找模块，彻底解决无法找到限制数地址、内存限制数显示为”未知“的现象。
  * 修改缓存类型，提高兼容性。

2008.11.12  V2.1.0.33
  + 增加原生64位的TCPZ64.exe。不喜欢在任务管理器中看到*32小尾巴的可以用TCPZ64.exe。普通用户建议使用TCPZ.exe，32/64位通用。
  * 改进查找方法。
  * 提高Windows XP内存限制数至1000。
  * 修正在Windows 7 x64上加载驱动失败的情形。
  * 修正与多核CPU的兼容性问题。

2008.11.29  V2.2.0.35
  + 虚拟驱动增加自定义设置上限选项，提高XP上限范围，为Vista/Windows7增加无限连接数选项。
  + GUI程序增加F5/F6键截图功能。需要GDI+支持。
  * GUI程序添加Vista UAC权限提示的manifest。XP SP2可能不兼容，请升级SP，或继续使用V2.1版TCP-Z。
  * GUI程序改为单文件便携版本。
  
2008.12.16  V2.2.1.36
  * 修改读注册表函数，增加一个空参数iNullAction，避免NOD32错认作病毒。
  # 此版本没有其它功能的升级和修改。

-------------------------------------------------------
2008.12.27  V2.3.0.42
  * 修改程序文件的数字签名标识。（感谢NOD32中文站版主的提醒）
  + GUI程序，全面改进UI，感谢完美天空美工制作的Skin。
  + GUI程序，增加显示半开连接数内存限制与文件限制的地址。（为了版本兼容，在64位系统中只显示内存地址低位部分。）
  * GUI程序，修正识别旧版本因查找地址范围设置过小而无法识别的Windows 7 Build 6.1.6936.0的Tcpip.sys文件，以及Windows 2003 5.2.3790.4331文件。
  * GUI程序，修正在Windows XP SP3 32位下无法禁用WFP而导致修改文件失败的bug。
  # 驱动程序没有变动。

2008.12.29  V2.3.1.43
  * GUI程序，文件补丁部分，去除Windows XP下禁用WFP的代码，兼容性不好。

2009.01.08  V2.4.0.46
  + 支持Windows 7 x64 6.1.7000.0内存补丁。
  + GUI程序，增加支持键盘操作。感谢Aldares。 Ctrl+Tab＝切换标签页；Tab＝切换控件。
  * GUI程序，文件补丁部分，改进Windows XP下禁用WFP兼容性问题。 感谢BRD-IlLusioN-CCCP。
  * GUI程序，修正界面在非标准DPI下显示错位的问题。

2009.02.05, V2.5.1.50
  + GUI程序，增加识别tcpip.sys是否是未经修改的原版文件。
  * GUI程序，支持早期版本的 Windows XP x64 SP1。
  * GUI程序与驱动程序，支持 Windows Vista SP2 RC v.275, x64, 6.0.6002.16659。

2009.03.07, V2.6.0.64 Beta
  + 支持更多的语言。 German by Mods.sub.cc; Italian by FSoft; Polish by PrEzi; Romanian by Misaki-kun & StelistCristi. Thank them.
  + 增加统计传入、传出、连接失败、成功率等统计信息。
  + 增加为每个程序单独统计各种连接数的功能。
  + 迷你栏;
  + 更改实时数据标签的对齐方式。
  + 退出时保存窗口设置。

2009.03.16 V2.6.0.66
  + 支持更多的语言。 Bulgarian by ExaFlop; Swedish by Marshall Mathers; Thai by Pruthisith; Turkish by Yekta Kayman; Ukraine by ShriEkeR. Thank them!
 
2009.04.06 V2.6.1.72
  + 支持更多的语言。 Russian by Serhii Hlodin, Mixa, Qui Sum; Korean by deuxdoom; French by jacklours; Portugese by Anubis. Thank them!
  + tcpz.ini增加选项设置图表的 Y 轴上限。
  * 修正： Y轴标签在大字体或超过4位数时显示错位。“传入”连接显示范围错误。
  * 修正： 透明度百分比菜单显示错误。
  * 修正： 部分机器不能正常显示网卡速度。
  * 修正： 网卡流量超过 4GB 时显示归零。
  * 修正： 不能正常接收关机消息。
  * 编译工具改为： WDK 6001.18002.

2009.04.09 V2.6.2.75
  * 在 Vista/Windows 7 下隐藏不必要的隧道类型网络接口。
  * 增加查找范围，支持 Windows 7 6.1.7077.0 (winmain_win7rc.090404-1255), x86.
