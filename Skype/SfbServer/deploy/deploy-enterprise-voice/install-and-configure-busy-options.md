---
title: Установка и настройка параметров занятости в Skype для бизнеса Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Прочитайте о том, как установить и настроить параметры «занят» в Скайп для Business Server.
ms.openlocfilehash: 2cca6c3b1075e1f5c7f1674a8e5609b49300bba6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884105"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Установка и настройка параметров занятости в Skype для бизнеса Server

Прочитайте о том, как установить и настроить параметры «занят» в Скайп для Business Server.

Параметры занятости были представлены в накопительном пакете обновлений за июль 2016 года и определяют политику голосовой связи, которая задает порядок обработки входящих звонков, поступающих во время обычного, удерживаемого или конференц-звонка. В зависимости от настроек новые или входящие звонки могут отклоняться с сигналом "занято" или переадресовываться на голосовую почту.

Если для организации включены параметры занятости, все ее пользователи, независимо от наличия доступа к корпоративной голосовой связи, могут использовать следующие параметры конфигурации:

- Сигнал занятости — если пользователь занят, все входящие звонки отклоняются и подается сигнал "занято".

- Голосовая почта — если пользователь занят, все входящие звонки переадресуются на голосовую почту.

Независимо от установленных параметров занятости, во время обычного, удерживаемого или конференц-звонка пользователи могут выполнять новые звонки.  

Дополнительные сведения о функции «занят» параметры в разделе [Планирование занят параметры Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Установка 

Убедитесь, что у вас есть последней версии Скайп для установки Business Server и, что установлены последние обновления. Для этого сначала остановите все службы и запустите Скайп для установки обновлений Business Server следующим образом:

1. Выполните команду Stop-CsWindowsService.

2. Запустите файл SkypeServerUpdateInstaller.exe для каждого сервера переднего плана в пуле.

3. Если необходимо реализовать отработку отказа на серверах обеспечения связи в филиалах, запустите установщик SkypeServerUpdateInstaller.exe на каждом из таких серверов.

Установщик разворачивает последнюю версию приложения параметров занятости, однако оно не будет включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.

1. Выполните командлет [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) глобально Включение параметров «занят», как показано в следующем примере:

  ```
  Set-CsVoicePolicy -EnableBusyOptions $true
  ```

2. Затем, если для сайта настроена политика голосовой связи, необходимо включить параметры занятости для этой политики следующим образом.

    Во-первых выполните [Командлет Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) для получения имени узла.

   ```
   Get-CsSite
   ```

    Используйте значение Identity (например: Site: Redmond1) извлекается из командлет Get-CsSite для получения политики голосовой связи сайта, как показано ниже:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Если для сайта существует политика голосовой связи, выполните следующую команду:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Затем выполните командлет [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , чтобы добавить параметры «занят» в список серверных приложений, как показано в следующем примере:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Полное доменное имя % необходимо заменить на полное доменное имя конкретного пула.

4. Затем выполните командлет [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) , чтобы обновить роли управления ДОСТУПОМ на основе ролей доступ по командлетам занят параметры, как показано в следующем примере:

   ```
   Update-CsAdminRole
   ```

5. И, наконец запустите Скайп для служб Business Server Windows на всех серверах переднего плана во всех пулах, где «занят» параметры была установлена и включена, выполнив команду [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>Настройка

Чтобы настроить параметры «занят», используйте командлет [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Например, следующая команда задает параметры занятости для пользователя "Ken Myer". В такой конфигурации при поступлении звонка этому пользователю во время активного звонка возвращается сигнал "занято":

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

В следующем примере эта команда задает параметры занятости для пользователя "Chrystal Velasquez". В такой конфигурации новые входящие звонки, поступающие этому пользователю во время активного звонка, переадресуются на голосовую почту:


```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Сведения о занятости параметры конфигурации можно извлечь с помощью командлета [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . В следующем примере возвращается текущее значение «занят» параметры «KenMyer@Contoso.com»:

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Параметры «занят» можно удалить с помощью командлета [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . Следующая команда удаляет параметры занятости для пользователя "Ken Myer":

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Подробные сведения о командлетах, используется для настройки параметров «занят» см в разделе справочные материалы для [Набора CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

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

После установки параметров «занят», вы можете проверить, что установка прошла успешно, с помощью командлета [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверов приложений. Если параметры занятости установлены надлежащим образом, этот командлет вернет следующую конфигурацию этой функции:

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

Также можно использовать средство просмотра событий Windows для проверки успешности установки параметров «занят» и что Скайп для Business Server успешно загружен параметры «занят». Чтобы проверить параметры «занят», откройте **окно просмотра событий -\> журналы служб - приложений и\> Скайп (или Lync) сервера** и выполните поиск события ID = 30253.