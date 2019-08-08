---
title: Установка и настройка параметров занятости в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Узнайте о том, как установить и настроить параметры доступности в Skype для бизнеса Server.
ms.openlocfilehash: a0fd235d5db645035ac9a6344c233dfe12a78b7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240312"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Установка и настройка параметров занятости в Skype для бизнеса Server

Узнайте о том, как установить и настроить параметры доступности в Skype для бизнеса Server.

Параметры занятости были представлены в накопительном пакете обновлений за июль 2016 года и определяют политику голосовой связи, которая задает порядок обработки входящих звонков, поступающих во время обычного, удерживаемого или конференц-звонка. В зависимости от настроек новые или входящие звонки могут отклоняться с сигналом "занято" или переадресовываться на голосовую почту.

Если для организации включены параметры занятости, все ее пользователи, независимо от наличия доступа к корпоративной голосовой связи, могут использовать следующие параметры конфигурации:

- Сигнал занятости — если пользователь занят, все входящие звонки отклоняются и подается сигнал "занято".

- Голосовая почта — если пользователь занят, все входящие звонки переадресуются на голосовую почту.

Независимо от установленных параметров занятости, во время обычного, удерживаемого или конференц-звонка пользователи могут выполнять новые звонки.  

Дополнительные сведения о функции параметров занятости см. в статье [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Установка 

Убедитесь, что у вас установлена последняя версия Skype для бизнеса Server и что вы установили Последнее исправление. Для этого сначала остановите все службы, а затем запустите программу установки обновления для Skype для Business Server, как описано ниже.

1. Выполните команду Stop-CsWindowsService.

2. Запустите файл SkypeServerUpdateInstaller.exe для каждого сервера переднего плана в пуле.

3. Если необходимо реализовать отработку отказа на серверах обеспечения связи в филиалах, запустите установщик SkypeServerUpdateInstaller.exe на каждом из таких серверов.

Установщик разворачивает последнюю версию приложения параметров занятости, однако оно не будет включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.

1. Запустите командлет [Set-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) , чтобы включить параметры доступности, как показано в следующем примере.

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Затем, если для сайта настроена политика голосовой связи, необходимо включить параметры занятости для этой политики следующим образом.

    Сначала запустите [Get-кссите](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) , чтобы получить имя сайта:

   ```
   Get-CsSite
   ```

    Используйте значение удостоверения (например, сайт: Redmond1), полученное из Get-Кссите, чтобы получить политику голосовой связи для сайта, как описано ниже.

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Если для сайта существует политика голосовой связи, выполните следующую команду:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Затем выполните командлет [New-кссервераппликатион](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , чтобы добавить параметры Busy в список серверных приложений, как показано в следующем примере:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Вы должны заменить% FQDN% полным доменным именем определенного пула.

4. Затем выполните командлет [Update-ксадминроле](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) , чтобы обновить роли управления доступом на основе РОЛЕЙ (RBAC) для командлетов параметров Busy, как показано в следующем примере.

   ```
   Update-CsAdminRole
   ```

5. Наконец, запустите команду [Start-ксвиндовссервице](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) на всех серверах, на которых установлены и включены службы Windows для бизнеса Server, на все серверы переднего плана, на которых установлен и включен параметр Busy.

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>Настройка

Для настройки параметров занятости используйте командлет [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  

Например, следующая команда задает параметры занятости для пользователя "Ken Myer". В такой конфигурации при поступлении звонка этому пользователю во время активного звонка возвращается сигнал "занято":

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

В следующем примере эта команда задает параметры занятости для пользователя "Chrystal Velasquez". В такой конфигурации новые входящие звонки, поступающие этому пользователю во время активного звонка, переадресуются на голосовую почту:

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Чтобы извлечь сведения о конфигурации параметров занятости, используйте командлет [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx). В следующем примере возвращаются значения параметров Busy для "KenMyer@Contoso.com":

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Чтобы удалить параметры занятости, используйте командлет [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx). Следующая команда удаляет параметры занятости для пользователя "Ken Myer":

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Подробные сведения о командлетах, используемых для настройки параметров доступности, приведены в справочных материалах для [Set-ксбусйоптионс](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-Ксбусйоптионс](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-ксбусйоптионс](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Включение ведения журналов

Чтобы включить ведение журналов с использованием соответствующей централизованной службы, введите следующую команду:

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Проверка и устранение неполадок

После установки параметров доступности вы можете убедиться, что установка выполнена успешно с помощью командлета [Get-кссервераппликатион](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) , чтобы получить список серверных приложений. Если параметры занятости установлены надлежащим образом, этот командлет вернет следующую конфигурацию этой функции:

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

Кроме того, можно использовать средство просмотра событий Windows, чтобы убедиться, что установка параметров доступности успешно завершилась, и что параметры доступности в Skype для бизнеса Server успешно загружены. Чтобы проверить параметры доступности, откройте **окно просмотра событий\> — журналы приложений и служб\> — Skype (или LYNC)** и найдите событие ID = 30253.
