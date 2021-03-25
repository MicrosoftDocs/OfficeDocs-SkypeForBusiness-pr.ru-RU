---
title: Обслуживание и работа помещений Microsoft Teams
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
description: В этой теме вы узнаете об управлении комнатами Microsoft Teams, системами комнат Skype нового поколения.
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117437"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Обслуживание и работа помещений Microsoft Teams 
 
Прочел эту статью, чтобы узнать об управлении комнатами Microsoft Teams, системами комнат Skype нового поколения.
  
Комнаты Microsoft Teams — это последнее решение Корпорации Майкрософт для проведения собраний, предназначенное для преобразования комнаты для собраний в богатый возможности для совместной работы. Пользователям понравится знакомый интерфейс Microsoft Teams или Skype для бизнеса, а ИТ-администраторы по достоинству оценят простое развертывание и управление приложением для собраний Skype 10. Комнаты Microsoft Teams разработаны таким образом, чтобы использовать существующее оборудование, такое как панели УПРАВЛЕНИЯ, для простоты установки, чтобы вывести Microsoft Teams или Skype для бизнеса в свою комнату для собрания.
  
Благодаря дополнительной конфигурации удаленное управление возможно с помощью microsoft Azure Monitor, как описано в описании в плане управления комнатами Microsoft Teams с помощью [Azure Monitor,](azure-monitor-plan.md)развертывание управления комнатами Microsoft Teams с помощью [Azure Monitor,](azure-monitor-deploy.md)управление устройствами комнат Microsoft Teams с помощью [Azure Monitor.](azure-monitor-deploy.md) Вы также можете [удаленно управлять настройками](xml-config-file.md)консоли комнат Microsoft Teams с помощью XML-файла конфигурации, который включает применение пользовательской темы отображения. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Сбор журналов в комнатах Microsoft Teams
<a name="Logs"> </a>

Для сбора журналов необходимо вызвать сценарий сбора журналов, который входит в состав приложения "Комнаты Microsoft Teams". В режиме администрирования запустите командную строку с повышенными привилегиями и выполните следующую команду.
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Журналы будут записываться в ZIP-файле в каталоге c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Параметры центрального дисплея
<a name="Display"> </a>

Настройте расширенный режим для центрального дисплея. Это гарантирует, что пользовательский интерфейс консоли не будет дублироваться на этом дисплее при циклике питания на дисплее.
  
> [!NOTE]
> Если вы хотите, чтобы передняя панель отображалась для автоматического переключения на активный источник видео (например, консоль MTR) при переходе из режима ожидания, должны быть выполнены определенные условия. Эта функция является необязательной, но поддерживается программным обеспечением для комнат Microsoft Teams, при условии, что оборудование, на которое она предоставляется, поддерживается. Телевизор, используемый перед комнатой, должен поддерживать функцию управления "Потребительские электронные системы" (CEC) HDMI.  В зависимости от выбранной док-станции или консоли (которая может не поддерживать CEC, обратитесь к документации производителя) для обеспечения желаемого поведения может потребоваться контроллер [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) из Надстройки или [Ex и HD CTL 100](https://www.extron.com/article/hdctl100ad) из Exstation. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Сброс помещений Microsoft Teams (восстановление до заводских насов)
<a name="Reset"> </a>

Если помещения Microsoft Teams работают не так, возможно, вам поможет сброс до заводских нас. Для этого воспользуйтесь средством восстановления комнат [Microsoft Teams и](recovery-tool.md) следуйте инструкциям по восстановлению до заводских нас.

> [!NOTE]
> Существует известная проблема, из-за которой комнаты Microsoft Teams могут стать неиспользоваемыми, если команда "Сохранить мои файлы": удаление приложений и **параметров,** но сохранение личных файлов в процессе сброса Windows. Не *используйте* этот параметр.
  
## <a name="supported-remote-options"></a>Поддерживаемые параметры удаленной работы
<a name="RemoteOptions"> </a>

В таблице ниже приводится сводка возможных удаленных операций и методов их выполнения.
  

|Рабочая группа |Без присоединения к домену|Присоединение к домену|
|:-----|:-----|:-----|
|Перезапуск  <br/> |Центр администрирования Teams  <br/> Удаленный рабочий стол  <br/> Удаленная среда PowerShell  <br/> | <br/>Удаленный рабочий стол (требуется дополнительная настройка)  <br/> Remote Powershell (требуется дополнительная настройка)  <br/> Configuration Manager  <br/> |
|Обновление ОС  <br/> |Обновление Windows  <br/> |Обновление Windows  <br/> WSUS  <br/> |
|Обновление приложения  <br/> |	Магазин Windows  <br/> |Магазин Windows  <br/> Configuration Manager  <br/> |
|Config учетной записи  <br/> |Центр администрирования Teams  <br/> |Центр администрирования Teams  <br/> |
|Журналы доступа  <br/> |Центр администрирования Teams  <br/> |Центр администрирования Teams <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Настройка групповой политики для комнат Microsoft Teams
<a name="GroupPolicy"> </a>

В этом разделе параметров системы, от которых зависит правильное функционирование комнат Microsoft Teams. При присоединении комнат Microsoft Teams к домену убедитесь, что групповые политики не переопределяют параметры, которые параметров в таблице ниже.
  

|Параметр|Разрешает|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Обеспечивает загрузку помещений Microsoft Teams  <br/> |
|Power \> Management: выключение экрана через 10 минут в ac  <br/> Power Management — \> в ac, никогда не перенаправление системы в спящий режим  <br/> |Позволяет комнатам Microsoft Teams автоматически отключать вложенные дисплеи и пробуждаться  <br/> |
|net accounts /maxpwage:unlimited  <br/> Эквивалентные средства отключения срока действия паролей в локальной учетной записи. Невыполнение этого действия в конечном итоге приведет к сбою при работе учетной записи Skype, которая жалуются на просроченный пароль. Обратите внимание, что это влияет на все локальные учетные записи на компьютере, поэтому неудачная настройка также приведет к истечении срока действия учетной записи администратора в поле.  <br/> |Позволяет учетной записи Skype всегда выполнять вход.  <br/> |
   
Перенос файлов с помощью групповых политик обсуждается в статье ["Настройка элемента файла".](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

> [!NOTE]
> Если устройство комнат Microsoft Teams совместимо со следующей версией ОС Windows 10, оно автоматически обновляется с помощью Обновления Windows. Устройство комнат Microsoft Teams не должно обновляться до следующей версии Windows 10 вручную или с помощью групповых политик Windows Update для бизнеса (WUFB) "Выберите уровень готовности Windows для получения обновлений" и "Выберите время получения сборок и обновлений функций" на сайте GPO. Известно, что устройство с включенными групповыми политиками имеет проблемы с обновлением ОС Windows 10 с помощью приложения Microsoft Teams Rooms.

## <a name="remote-management-using-powershell"></a>Удаленное управление с помощью PowerShell
<a name="RemotePS"> </a>

С помощью PowerShell можно выполнять следующие операции управления удаленно (примеры сценариев см. в таблице ниже):
  
- Получение списка подключенных устройств
- Получение сведений о состоянии приложений
- Получение сведений о системе
- Перезагрузка системы
- Получение журналов
- Передача файлов (требуется доступ к домену в комнатах Microsoft Teams)
    
> [!NOTE]
> По умолчанию эта возможность выключена. Для выполнения действий, которые приведены ниже, необходимо включить удаленную среду PowerShell для своей среды в системе комнат Microsoft Teams. Сведения о том, как включить удаленную powerShell, можно найти в документации **[enable-PSRemoting.](/powershell/module/microsoft.powershell.core/enable-psremoting)**
  
Например, чтобы включить удаленную оболочку PowerShell, можно выполнить указанные ниже действия.
  
1. Во sign in as Admin on a Microsoft Teams Rooms device.
2. Откройте командную подсказку PowerShell с повышенными уровнями.
3. Введите следующую команду: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Откройте локонную политику безопасности  и добавьте группу безопасности "Администраторы" в группу "Параметры  >  **безопасности",** чтобы получить доступ к назначению прав пользователя "Параметры безопасности"  >    >  **из сети.**

Чтобы совершить операцию по управлению, выполните указанные ниже действия.
  
1. Во sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.
2. Откройте на компьютере обычную командную команду PowerShell.
3. Скопируйте текст команды из приведенной ниже таблицы и вкопируйте его при запросе.
4. Замените  `<Device fqdn>` поля значениями FQDN, подходящими для вашей среды.
5. Замените имя файла и локальный путь к SkypeSettings.xml  *\<path\>*  файла конфигурации (или изображения темы).
    
Для вложенных устройств
  
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

Нажмите XML-файл конфигурации (или изображение темы)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Обновления программного обеспечения
<a name="SWupdate"> </a>

По умолчанию microsoft Teams Rooms пытается подключиться к Магазину Windows, чтобы получить последнюю версию программного обеспечения комнат Microsoft Teams, поэтому устройство требует регулярного доступа к Интернету. Прежде чем обращаться в службу поддержки Майкрософт, убедитесь, что устройство комнат Microsoft Teams загружено с последней версией приложения.
  
По умолчанию комнаты Microsoft Teams подключаются к Обновлению Windows для обновления операционной системы и USB-периферийного устройства, а затем устанавливают их в нестройное время. Чтобы указать часы работы, войдите в учетную запись администратора и запустите приложение "Параметры".
  
Если вы хотите управлять обновлениями вручную и не можете выполнять обычную процедуру для распространения автономных приложений [в Microsoft Store](https://businessstore.microsoft.com/store) для бизнеса, вы можете приобрести соответствующий файл APPX и зависимости из комплекта развертывания (из инструкций по настройке консоли комнат Microsoft [Teams),](console.md)которые можно использовать с Configuration Manager. [](/microsoft-store/distribute-offline-apps) [](https://go.microsoft.com/fwlink/?linkid=851168) Выпуск набора развертывания отстает от выпуска магазина, поэтому он может не всегда соответствовать последней доступной сборке.
  
### <a name="to-update-using-powershell"></a>Обновление с помощью Powershell

1. Извлекать пакет из установного [MSI-пакета](https://go.microsoft.com/fwlink/?linkid=851168) к совместному доступу устройства.
2. Запустите следующий сценарий, который предназначен для устройств с комнатами Microsoft Teams, сменив его на \<share\> устройство с учетом необходимости:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Режим администрирования и управление устройствами
<a name="AdminMode"> </a>

Некоторые функции управления, например установка частного сертификата ЦС вручную, требуют помещения устройства Surface Pro в режим администрирования. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Переключение в режим администрирования и обратно при запуске приложения "Комнаты Microsoft Teams"

1. Повесь трубку со звонками и вернись на домашний экран.
2. Выберите значок шестеренки и в меню (доступны такие параметры, как "Параметры", **"Доступность"** и "Перезагрузка **устройства").**
3. Выберите **Параметры**.
4. Введите пароль администратора. Откроется экран настройки.  Если устройство не присоединилось к домену, по умолчанию будет использоваться локализованная административная учетная запись (имя пользователя "Администратор"). Пароль по умолчанию для этой учетной записи — "sfb", и пароль можно изменить как можно скорее. Если компьютер присоединяется к домену, вы можете войти с помощью соответствующей учетной записи с привилегированным доменом. 
5. Выберите **"Параметры Windows"** в левом столбце.
6. Выберите **Go to Admin Sign-in** (Перейти на страницу входа администратора).
7. Введите пароль администратора. Будет выполнен выход из приложения, а затем откроется экран входа Windows. 
8. Выполните вход в систему с использованием учетных данных администратора. У вас будут необходимые права для управления устройством.
9. Выполните необходимые административные задачи.
10. Выйдите из учетной записи с правами администратора.
11. Вернись в комнаты Microsoft Teams, выбрав значок учетной записи пользователя в левой части экрана и выбрав **Skype.**
    
    Если пользователя **Skype** нет в списке,  может потребоваться выбрать другого пользователя, ввести в качестве имени пользователя **.\skype** и войти в приложение.
    
Консоль снова находится в обычном режиме работы. Если клавиатура еще не прикреплена, к устройству необходимо будет прикрепить клавиатуру. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Переключение в режим администрирования и обратно при сбое приложения "Комнаты Microsoft Teams"

1. Быстро нажмите клавишу Windows пять раз подряд. Откроется экран входа Windows. 
2. Выполните вход в систему с использованием учетных данных администратора.
3. Выполните необходимые административные задачи.
4. По завершению перезапустите компьютер.

    > [!NOTE]
    > При использовании этого метода пользователь Skype не отключается или не изящно прекращает работу приложения, но вы будете использовать его, если приложение не отвечает, а другой метод недоступны. 

   Консоль перезапустится в обычный режим работы с приложением "Комнаты Microsoft Teams". Вы можете удалить клавиатуру, если она была подключена, чтобы выполнить эту процедуру.
   ## <a name="troubleshooting-tips"></a>Советы по устранению неполадок
   <a name="TS"> </a>

- Приглашения на собрания могут не отображаться при отправлении за границы домена (например, между двумя компаниями). В таких случаях ИТ-администраторы должны решить, следует ли разрешить внешним пользователям планировать собрание.
- Комнаты Microsoft Teams не поддерживают перенаправление автообнаружия Exchange через Exchange 2010.
- Как правило, ИТ-администраторы отключать любые конечные точки звука, которые не предполагается использовать.
- Если в режиме предварительного просмотра комнаты выводится зеркальное отражение, ИТ-администратор может устранить эту проблему, выключив и снова включив питание камеры или настроив зеркальное отражение изображения с помощью пульта дистанционного управления камерой.
- Известны случаи утери доступа к сенсорному экрану консоли. В таких случаях проблему иногда можно решить путем перезапуска системы комнат Microsoft Teams.
- Известны случаи исчезновения локального звукового сигнала при подключении компьютера к консоли с помощью кабеля. Эту проблему можно устранить путем перезагрузки компьютера.
