4. Функцию: "Отключить поиск через Bing в меню "Пуск"" отображать только, если регион США

```powershell
(Get-ItemPropertyValue -Path "HKCU:\Control Panel\International\Geo" -Name Nation) -eq 244
```

C# (NetFramework 4.8):

* <https://docs.microsoft.com/en-us/dotnet/api/system.globalization.regioninfo.geoid?view=netframework-4.8>
* <https://docs.microsoft.com/ru-ru/windows/win32/intl/table-of-geographical-locations> (244)

1. Добавить возможность копировать описание функции, нажав в контекстном меню рамки "Копировать"

2. Функция для экспорта ico из файла. Понадобится в будущем

<https://gist.github.com/darkfall/1656050#gistcomment-1332369>

```powershell
#
Add-Type -AssemblyName System.Drawing
[System.Drawing.Icon]::ExtractAssociatedIcon("C:\WINDOWS\system32\control.exe").ToBitmap().Save("C:\Desktop\1\1.ico")

#
$Path = "$env:SystemRoot\system32\control.exe"
$FileName = "C:\Desktop\1\1.ico"
$Format = [System.Drawing.Imaging.ImageFormat]::Icon
Add-Type -AssemblyName System.Drawing
$Icon = [System.Drawing.Icon]::ExtractAssociatedIcon($Path) | Add-Member -MemberType NoteProperty -Name FullName -Value $Path -PassThru
$Icon.ToBitMap().Save($FileName,$Format)
```
3. <https://github.com/WindowsNotifications?q=&type=&language=c%23>

4. <https://pastebin.com/mKEFmnC1>

============================================================================================

## Кастомный scrollviewer

<http://codesdirectory.blogspot.com/2013/01/wpf-scrollviewer-control-style.html>

## Кастомный dots line progress bar

<https://www.jeff.wilcox.name/2010/08/performanceprogressbar/>

## LoadingRing

<https://github.com/zeluisping/LoadingIndicators.WPF/blob/master/src/LoadingIndicators.WPF/Styles/LoadingRing.xaml>

## Работа с JSON

* <http://www.jsonutils.com/>
* <https://jsonformatter.org/json-pretty-print>

## Регулярные выражения

<https://regex101.com/>

<http://alexweinberger.com/main/pinning-network-program-taskbar-programmatically-windows-10/>

## Получить номер билда

```powershell
[System.Environment]::OSVersion.Version.Build
Get-ItemPropertyValue -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion" -Name CurrentBuild
```

<https://fastspring.com>