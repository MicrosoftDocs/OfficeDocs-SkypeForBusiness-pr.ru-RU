---
title: Комнаты Microsoft Teams обслуживания и операций
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой теме вы узнаете об управлении Комнаты Microsoft Teams, следующего поколения системы Skype комнат.
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117437"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Комнаты Microsoft Teams обслуживания и операций 
 
В этой теме вы узнаете об управлении Комнаты Microsoft Teams, следующего поколения системы Skype комнат.
  
Комнаты Microsoft Teams — это последнее решение Майкрософт для проведения собраний, предназначенное для преобразования комнаты для собраний в насыщенный и совместный процесс. Пользователям понравится знакомый интерфейс Microsoft Teams или Skype для бизнеса, и ИТ-администраторы по достоинству оценят простое развертывание и управление Windows 10 Skype приложении для собраний. Комнаты Microsoft Teams предназначен для использования существующего оборудования, например панелей СЛФ, для упростит установку Microsoft Teams или Skype для бизнеса в комнате собрания.
  
Благодаря дополнительной конфигурации удаленное управление можно использовать Microsoft Azure Monitor, как описано в Комнаты Microsoft Teams планирования с помощью [Azure Monitor](azure-monitor-plan.md), Развертывание управления Комнаты Microsoft Teams с помощью [Azure Monitor](azure-monitor-deploy.md), управление устройствами Комнаты Microsoft Teams с помощью [Azure Monitor.](azure-monitor-deploy.md) Вы также можете управлять Комнаты Microsoft Teams консоли удаленно с помощью [XML-файла](xml-config-file.md)конфигурации, который включает применение пользовательской темы отображения. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Сбор журналов Комнаты Microsoft Teams
<a name="Logs"> </a>

Для сбора журналов необходимо вызвать сценарий сбора журналов, который входит в Комнаты Microsoft Teams приложения. В режиме администрирования запустите командную строку с повышенными привилегиями и выполните следующую команду.
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Журналы будут записываться в ZIP-файле в каталоге c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Параметры центрального дисплея
<a name="Display"> </a>

Настройте расширенный режим для центрального дисплея. Это гарантирует, что пользовательский интерфейс консоли не будет дублироваться на этом дисплее при циклике питания на дисплее.
  
> [!NOTE]
> Если вы хотите, чтобы при переходе из режима ожидания источник видео автоматически переключался на активный источник видео (например, консоль MTR), то при этом должны быть выполнены определенные условия. Эта функция является необязательной, но поддерживается программным обеспечением Комнаты Microsoft Teams, которое поддерживает оборудование. Телевизор, используемый в качестве переднего экрана комнаты, должен поддерживать функцию управления потребительскими электронными устройствами (CEC) HDMI.  В зависимости от выбранной док-станции или консоли (которая может не поддерживать CEC, обратитесь к документации производителя), для обеспечения нужного поведения может потребоваться геймпад [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) из КомпанииГриголь или [Exа hd CTL 100](https://www.extron.com/article/hdctl100ad) из Exstation. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Комнаты Microsoft Teams Сброс (восстановление до заводских цехов)
<a name="Reset"> </a>

Если Комнаты Microsoft Teams не работает, возможно, вам поможет сброс до заводских населений. Для этого воспользуйтесь средством восстановления Microsoft Teams [комнаты](recovery-tool.md) и следуйте инструкциям по восстановлению до заводских насайтов.

> [!NOTE]
> Известная проблема, из-за которой Комнаты Microsoft Teams может стать непригодной для работы, если во время сброса параметр Сохранить мои файлы : удаление приложений и **параметров,** но сохранение личных файлов Windows. Не *используйте* этот параметр.
  
## <a name="supported-remote-options"></a>Поддерживаемые параметры удаленной работы
<a name="RemoteOptions"> </a>

В таблице ниже приводится сводка возможных удаленных операций и методов их выполнения.
  

|Рабочая группа |Без присоединения к домену|Присоединение к домену|
|:-----|:-----|:-----|
|Перезапуск  <br/> |Teams центре администрирования  <br/> Удаленный рабочий стол  <br/> Удаленная среда PowerShell  <br/> | <br/>Удаленный рабочий стол (требуется дополнительная настройка)  <br/> Remote Powershell (требуется дополнительная настройка)  <br/> Configuration Manager  <br/> |
|Обновление ОС  <br/> |Обновление Windows  <br/> |Обновление Windows  <br/> WSUS  <br/> |
|Обновление приложения  <br/> |	Магазин Windows  <br/> |Магазин Windows  <br/> Configuration Manager  <br/> |
|"Config учетной записи"  <br/> |Teams центре администрирования  <br/> |Teams центре администрирования  <br/> |
|Журналы доступа  <br/> |Teams центре администрирования  <br/> |Teams центре администрирования <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Настройка групповой политики для Комнаты Microsoft Teams
<a name="GroupPolicy"> </a>

В этом разделе параметров системы, Комнаты Microsoft Teams правильно работают. При присоединении Комнаты Microsoft Teams к домену убедитесь, что групповая политика не переопределяет параметры в таблице ниже.
  

|Параметр|Позволяет|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Позволяет Комнаты Microsoft Teams загрузку  <br/> |
|Power Management \> : выключение выключения экрана через 10 минут  <br/> Power Management — \> в ac, никогда не перенаправление системы в спящий режим  <br/> |Позволяет Комнаты Microsoft Teams отключать вложенные дисплеи и автоматически включать их  <br/> |
|net accounts /maxpwage:unlimited  <br/> Или аналогичное средство отключения срока действия пароля для локальной учетной записи. В противном случае учетной записи Skype через некоторое время не удастся выполнить вход и появится сообщение о том, что срок действия пароля истек. Имейте в виду, что это относится ко всем локальным учетным записям на компьютере. Поэтому, если не задать этот параметр, срок действия учетной записи администратора также через некоторое время истечет.   <br/> |Позволяет учетной записи Skype всегда выполнять вход.  <br/> |
   
Перенос файлов с помощью групповых политик обсуждается в статье Настройка [элемента файла.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

> [!NOTE]
> Если Комнаты Microsoft Teams совместим со следующей версией Windows 10 OS, оно автоматически обновляется до следующей версии с помощью Windows Update. Комнаты Microsoft Teams устройство не должно быть обновлено до следующего выпуска Windows 10 вручную или с помощью включения групповых политик Windows Update for Business (WUFB) "Выбор уровня готовности Windows для обновлений, которые вы хотите получить" и "Выберите время получения предварительных сборков и обновлений функций" через GPO. Известно, что на устройстве с включенными групповыми политиками могут Windows 10 с обновлением ОС Комнаты Microsoft Teams приложением.

## <a name="remote-management-using-powershell"></a>Удаленное управление с помощью PowerShell
<a name="RemotePS"> </a>

Вы можете удаленно выполнять следующие операции управления с помощью PowerShell (примеры сценариев см. в таблице ниже):
  
- Получение списка подключенных устройств
- Получение сведений о состоянии приложений
- Получение сведений о системе
- Перезагрузка системы
- Получение журналов
- Передача файлов (требуется доменная Комнаты Microsoft Teams)
    
> [!NOTE]
> По умолчанию эта возможность выключена. Для выполнения операций, которые приведены ниже, необходимо включить Комнаты Microsoft Teams PowerShell для вашей среды на компьютере. Сведения о том, как включить удаленную powerShell, можно найти в документации на **[сайте Enable-PSRemoting.](/powershell/module/microsoft.powershell.core/enable-psremoting)**
  
Например, чтобы включить удаленную оболочку PowerShell, можно выполнить указанные ниже действия.
  
1. Во вход в качестве администратора на Комнаты Microsoft Teams устройстве.
2. Откройте командную команду PowerShell с повышенными уровнями.
3. Введите следующую команду: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Откройте локонную политику безопасности  и добавьте группу безопасности Администраторы в группу безопасности Параметры назначение прав пользователя локальным политикам Доступ к этому компьютеру  >    >    >  **из сети**.

Чтобы совершить операцию по управлению, выполните указанные ниже действия.
  
1. Во sign in to a PC with account credentials that have permission to run PowerShell commands on a Комнаты Microsoft Teams device.
2. Откройте на компьютере обычную командную команду PowerShell.
3. Скопируйте текст команды из приведенной ниже таблицы и вкопируйте его в нужное место.
4. Замените  `<Device fqdn>` поля значениями FQDN, соответствующими вашей среде.
5. Замените имя файла и локальный путь к SkypeSettings.xml  *\<path\>*  файла конфигурации (или изображения темы).
    
Получить вложенные устройства
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

получение состояния приложений;
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

получение сведений о системе;
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

перезагрузка системы;
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

получение журналов.
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Push-файл конфигурации XML (или изображение темы)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Обновления программного обеспечения
<a name="SWupdate"> </a>

По умолчанию Комнаты Microsoft Teams пытается подключиться к Windows Store, чтобы получить последнюю версию программного обеспечения Комнаты Microsoft Teams, поэтому для устройства требуется обычный доступ к Интернету. Перед тем как обращаться в службу поддержки Майкрософт, убедитесь, Комнаты Microsoft Teams устройство загружено с последней версией приложения.
  
По умолчанию Комнаты Microsoft Teams подключается к Windows обновления для получения обновлений операционной системы и USB-периферийного устройства и устанавливает их за нестройное время. Чтобы указать часы работы, войдите в учетную запись администратора и запустите приложение "Параметры".
  
Если вы хотите управлять обновлениями вручную и не можете выполнять обычную процедуру для [Microsoft Store для бизнеса](https://businessstore.microsoft.com/store) для распространения автономных [приложений,](/microsoft-store/distribute-offline-apps)вы можете приобрести соответствующий файл APPX и зависимости из набора развертываний [(из](https://go.microsoft.com/fwlink/?linkid=851168) инструкций для настройки консоли [Комнаты Microsoft Teams),](console.md)которые можно использовать с Configuration Manager. Выпуск набора развертывания отстает от выпуска магазина, поэтому он может не всегда соответствовать последней доступной сборке.
  
### <a name="to-update-using-powershell"></a>Обновление с помощью Powershell

1. Извлекать пакет из установного [MSI-пакета](https://go.microsoft.com/fwlink/?linkid=851168) в обойму устройства, к нему можно получить доступ.
2. Запустите следующий сценарий для Комнаты Microsoft Teams устройств, при необходимости изменив их на \<share\> "Поделиться":
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Режим администрирования и управление устройствами
<a name="AdminMode"> </a>

Некоторые функции управления, например установка частного сертификата ЦС вручную, требуют помещения Surface Pro в режим администрирования. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Переключение в режим администрирования и обратно при запуске Комнаты Microsoft Teams приложения

1. Повесь трубку с текущими звонками и вернись на домашний экран.
2. Выберите значок шестеренки и отпустите меню (доступны **Параметры,** **Специальными возможности** и **Перезапустить устройство).**
3. Выберите **Параметры**.
4. Введите пароль администратора. Откроется экран настройки.  Если устройство не присоединилось к домену, по умолчанию будет использоваться локализованная административная учетная запись (имя пользователя — "Администратор"). Пароль для этой учетной записи по умолчанию — sfb, который можно изменить как можно скорее. Если компьютер соединен с доменом, вы можете войти с помощью соответствующей учетной записи домена. 
5. Выберите **Windows Параметры** в левом столбце.
6. Выберите **Go to Admin Sign-in** (Перейти на страницу входа администратора).
7. Введите пароль администратора. Будет выполнен выход из приложения, а затем откроется экран входа Windows. 
8. Выполните вход в систему с использованием учетных данных администратора. У вас будут права, необходимые для управления устройством.
9. Выполните необходимые административные задачи.
10. Выйдите из учетной записи с правами администратора.
11. Вернись Комнаты Microsoft Teams, выбрав значок учетной записи пользователя в левой части экрана и выбрав **Skype**.
    
    Если **Skype** нет в списке, может потребоваться  выбрать другого пользователя, ввести в качестве имени пользователя **.\skype** и войти в нее.
    
Консоль снова находится в обычном режиме работы. Чтобы прикрепить клавиатуру к устройству, если она еще не вложена, следуя этой процедуре, вы можете сделать это. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Переключение в режим администрирования и обратно при сбое Комнаты Microsoft Teams приложения

1. Быстро нажмите клавишу Windows пять раз подряд. Откроется экран входа Windows.  
2. Выполните вход в систему с использованием учетных данных администратора.
3. Выполните необходимые административные задачи.
4. По завершению перезапустите компьютер.

    > [!NOTE]
    > При использовании этого метода пользователь Skype или постепенно прекращает работу приложения, но вы бы использовали его, если приложение не отвечало, а другой метод не был доступен. 

   Консоль перезапустится в обычный режим работы, и Комнаты Microsoft Teams приложение. Вы можете удалить клавиатуру, если она была прикреплена, чтобы можно было выполнить эту процедуру.
   ## <a name="troubleshooting-tips"></a>Советы по устранению неполадок
   <a name="TS"> </a>

- Приглашения на собрания могут не отображаться при отправлении за границы домена (например, между двумя компаниями). В таких случаях ИТ-администраторы должны решить, следует ли разрешить внешним пользователям планировать собрание.
- Комнаты Microsoft Teams не поддерживает перенаправление Exchange autoDiscover через Exchange 2010.
- Как правило, ИТ-администраторы отключать звуковые конечные точки, которые не намерены использовать.
- Если в режиме предварительного просмотра комнаты выводится зеркальное отражение, ИТ-администратор может устранить эту проблему, выключив и снова включив питание камеры или настроив зеркальное отражение изображения с помощью пульта дистанционного управления камерой.
- Известны случаи утери доступа к сенсорному экрану консоли. В таких случаях проблему иногда можно решить путем перезапуска Комнаты Microsoft Teams системы.
- Известны случаи исчезновения локального звукового сигнала при подключении компьютера к консоли с помощью кабеля. Эту проблему можно устранить путем перезагрузки компьютера.
