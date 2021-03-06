<I am Unicode File!>

TCP/IP монитор и патчер ограничения полуоткрытых соединений

Название проекта:	TCP-Z  (Сетевой монитор TCP-Z)
Поддерживаемые ОС:	Windows XP/2003/2008/Vista/Windows 7, All SP*, All 32bit (x86) / 64bit (x64)
Автор:			deepxw#126.com
Блог:			http://deepxw.lingd.net/article-1415261-1.html
			http://deepxw.blogspot.com   (English)

Изменение ограничений полуоткрытых (неполных) TCP соединений, увеличение производительности сети, ускорение загрузок файлов и других сетевых, одновременно выполняемых, задач. 

Особенности:
1) Безопасно и просто: изменение Tcpip.sys в памяти. Изменения вступают в силу незамедлительно. Перезагрузка компьютера не требуется. 

2) Расширенная совместимость: данная программа ищет ограничение по сигнатуре. Вам больше не нужно беспокоиться об обновлениях и исправлениях от Microsoft Update.
   Поддерживает все версии Windows которые имеют ограничения на количество полуоткрытых соединений.

3) Информативные графики: TCP-Z показывает количество открытых и полуоткрытых соединений, create depth, скорости входящего и исходящего потоков в режиме реального времени.
Приложение также показывает количество предупреждений в журнале событий, если превышен лимит на полуоткрытые соединения TCP. 

*******************
*  Использование  *
*******************
1) Вручную:
Используйте GUI-приложение tcpz.exe / tcpz64.exe для изменения значения ограничения полуоткрытых соединений.

При завершении работы программы TCP-Z изменения, которые внесены Вами, остаются в памяти и действуют до перезагрузки или выключения компьютера.

Эти изменения действуют временно. Перезагрузка компьютера вернет ограничения в начальное значение.
Вы должны вносить изменения на ограничения после каждой загрузки системы.

2) Автоматически:
Установите TCP-Z Virtual Device (виртуальный драйвер TCP-Z).

Виртуальный драйвер также вносит изменения в памяти по сигнатуре, но он более автоматизирован и имеет такую же эффективность, как и патчер файла tcpip.sys.

Драйвер устанавливает новое значение ограничений без ручного вмешательства. Используйте свойства драйвера (в диспетчере устройств) для установки необходимого значения ограничения.

Драйвер нужно установить только единожды. Новое значение лимита полуоткрытых соединений запоминается как пользовательское значение и устанавливается автоматически при каждой загрузке системы до тех пор, пока драйвер не будет удален (деинсталлирован).

Даже если будет установлен новый сервис-пак, Вам не нужно переустанавливать драйвер или выполнять какие-либо дополнительные действия.

Установка или удаление драйвера.
32bit, от имени администратора запустите программу: "TCPZ_Setup-x86.exe".
64bit, от имени администратора запустите программу: "TCPZ_Setup-x64.exe"


Эти две версии TCP-Z работают независимо. Выберите сами, что Вам более удобно.

Если Вы желаете внести изменения в файл tcpip.sys, пожалуйста, используйте утилиту "Universal Tcpip.sys Patch".


* Управление клавиатурой
Переключение между закладками			Ctrl + Tab
Переключение между полями			Tab
Подтверждение					Space
Сохранить окно TCP-Z в графический файл		F5
Сохранить рисунок экрана в графический файл	F6
 
* Параметры командной строки
tcpz.exe  -limit:200
tcpz.exe  -limit:200  -autoexit
tcpz.exe  -minimize

Если антивирусная программа блокирует загрузку драйвера tcp-z и это является причиной ошибки запуска tcp-z, Вы можете пропустить загрузку драйвера параметром командной строки:
tcpz.exe  -nodriver

К сожалению, без загрузки драйвера Вы не сможете использовать функцию внесения изменения в память.



******************************************
*  Возможные проблемы и пути их решения  *
******************************************
1. Для использования GUI-приложения его необходимо запустить от имени администратора посредством нажатия правой кнопки мышки на файле tcpz.exe и выбора соответствующего пункта меню.

2. На 64-х битной системе Vista/Win7 необходимо разрешить режим TESTSIGNING.
Для этого откройте командную строку в режиме администратора и выполните следующие команды:
bcdedit.exe -set loadoptions DDISABLE_INTEGRITY_CHECKS
bcdedit.exe -set TESTSIGNING ON
Перезагрузите компьютер для вступления в силу изменений.
Эти команды необходимо выполнить лишь один раз.
В режиме "Test Mode" Вы можете удалить данный водяной знак с помощью утилиты "RemoveWatermarkX64.exe".

32-х разрядные ОС не требуют данных операций.

3. Если приложение завершило свою работу аварийно и при следующей его загрузке идет сообщение об ошибке загрузки драйвера, запустите редактор реестра и удалите следующие секции:
32-х разрядная система:
REG DELETE HKLM\SYSTEM\CurrentControlSet\Services\tcpz-x86
64-х разрядная система:
REG DELETE HKLM\SYSTEM\CurrentControlSet\Services\tcpz-x64

Также удалите секцию: [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\Root\LEGACY_TCPZ-X86]
Перезагрузите компьютер и запустите приложение. Данная проблема должна решиться.

Некоторые антивирусные программы блокируют загрузку драйвера TCP-Z. Настройте их правила таким образом, чтобы они пропускали проверку драйвера и не препятствовали его загрузке.

4. В Windows XP поддерживаются патчер файла и памяти. В Vista/Windows 7 поддерживается только патчер памяти.

5. Если Вы хотите внести изменения в файл tcpip.sys в 64-х разрядной Windows XP, используйте 64-х разрядную версию TCPZ64.exe.

6. Windows 2003/2008 не имеет ограничений.

7. Vista / Windows 7 поддерживают опцию неограниченного количества полуоткрытых соединений в виртуальном драйвере TCP-Z. Установите значение лимита в 0 для включения этой возможности.


//History:
2008.09.14
  * Update to Unicode version, supports English/Chinese Simple/Chinese Traditional.

2008.09.21
  + Add a new installer.
  * Driver: Increased one finding action. Improve success rate.

2008.10.13
  + Support read limited value from tcpip.sys of Windows 7.

2008.10.23  V1.5.3.15
  + Read & display create depth from tcpip.sys.
  + Windows 7 M1 memory patch.
  * Can't read information from a few of net interface.

2008.10.30  V1.5.5.20
  + Windows 7 M3 (x86) memory patch.
  + Add warning message for AMD multi-core CPU user.

2008.11.01  V1.5.6.25
  + Windows 7 M3 (x64) memory patch. (Beta)
  * Windows XP file limited change to 1000.
  * Modified function of disable SFC in NT5.
  
2008.11.07  V2.0.0.30 beta
  * Modified all search function. Improve success rate.

2008.11.12  V2.1.0.33
  + Add tcpz64.exe, a native x64 program.
  * Modify search function.
  * Memory Limited of XP up to 1000.
  * Fix: compatibility of multi-core CPU.
  * Fix: fail to load driver in Windows 7 x64.

2008.11.29  V2.2.0.35
  + Virtual drive, add an option to custom limited value. Add an Unlimited option for Vista / Windows 7.
  + GUI program, capture screen by hot-key F5 / F6. It needs GDI+ support.
  * GUI program, add Vista UAC manifest. May not be compatible with XP SP2, you can upgrade Service Pack, or continue to use the V2.1 version of TCP-Z. 
  * GUI program be changed to a single file, portable version.

2008.12.16  V2.2.1.36
　* Modify TcpzQueryRegParameters(), Add a null parameter iNullAction, Avoid NOD32 report as virus.
　
2008.12.27  V2.3.0.42
　* Change digital signature of program files.
　+ GUI program, modify UI, add a beautiful skin.
　+ GUI program, display limited address in kernel memory, and file “Tcpip.sys”.
　  For compatibility, only display low part in 64bit OS.
　* Fixed: unknown file limited value in Windows 7 Build 6.1.6936.0, and Windows 2003 5.2.3790.4331.
　* Fixed: file patch Fail in windows XP SP3, because unable disable WFP.
　# Drivers has no changes.

2008.12.29  V2.3.1.43
  * GUI program, Remove the function of disable WFP, because Compatibility of this code is not so good.
    And because there is no disabled SFC, patch file will not to a 100% success, because Windows will automatically resume tcpip.sys.
    Another way, use Memory patch method.

2009.01.08  V2.4.0.46
  + Windows 7 x64 6.1.7000.0 Memory Patch.
  + GUI program, support keyboard control. Thank Aldares. 
                 Ctrl + Tab = switch tab; Tab = switch control.
  * GUI program, File Patch, improve compatibility of disable WFP in Windows XP. Thank BRD-IlLusioN-CCCP. 
  * GUI program, fixed, user interface in non-standard DPI can not correctly display. 

2009.02.05, V2.5.1.50
  * GUI program, identify whether tcpip.sys is the original file without modification.
  * GUI program, supports Windows XP x64 SP1 early version.
  * GUI program & Drivers, supports Windows Vista SP2 RC v.275, x64, 6.0.6002.16659.

2009.03.07, V2.6.0.64 Beta
  + Support more language. German by http://Mods.sub.cc; Italian by FSoft; Polish by PrEzi; Romanian by Misaki-kun & StelistCristi. Thank them.
  + Statistics of incoming and outgoging attempts...
  + Statistics of connections by each program.
  + Mini bar;
  + function of change the alignment of peak label.
  + Save setting at exit.

2009.03.16 V2.6.0.66
  + Support more language. Bulgarian by ExaFlop; Swedish by Marshall Mathers; Thai by Pruthisith; Turkish by Yekta Kayman; Ukraine by ShriEkeR. Thank them!
  
2009.04.06 V2.6.1.72
  + Support more language. Russian by Serhii Hlodin, Mixa, Qui Sum; Korean by deuxdoom; French by jacklours; Portugese by Anubis. Thank them!
  + Add options in tcpz.ini to customize the upper value of the graph.
  * Fixed: Y-axis label display not correct in big font. Error range of incoming connection graph.
  * Fixed: Transparence percentage display not correct.
  * Fixed: Can't display speed in some computer.
  * Fixed: Network traffic turn to zero when more than 4GB.
  * Fixed: Can't receive the shutdown message.
  * Build with WDK 6001.18002.

2009.04.09 V2.6.2.75
  * Hide the tunnel type of Adapter in Vista/Windows 7.
  * Increase the range of searcher, supports Windows 7 6.1.7077.0 (winmain_win7rc.090404-1255), x86.
