---
title: Установка и настройка параметров занятости для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830809"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Установка и настройка параметров занятости для Skype для бизнеса Server

Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.

Параметры занятости — это новая политика голосовой почты, представленная в накопительном обновлении за июль 2016 г., которая позволяет настроить обработку входящих вызовов, когда пользователь уже находится в звонках или конференциях или находится на удержании. Новые или входящие вызовы можно отклонить с сигналом "занято" или переадлить на голосовую почту.

Если для организации включены параметры занятости, все пользователи предприятия, как Корпоративная голосовая связь, так и пользователи, не Корпоративная голосовая связь, могут использовать следующие параметры конфигурации:

- Занят в "Занят". При этом новые входящие вызовы будут отклониться с сигналом "занято", если пользователь занят.

- Голосовая почта в службе "Занято". В которой новые входящие вызовы будут переадад частью голосовой почты, если пользователь занят.

Независимо от того, как настроены параметры занятости, пользователям в звонках или конференциях или звонках на удержании не помешает инициировать новые вызовы или конференции.

Дополнительные сведения о функции "Параметры занятости" см. в дополнительных сведениях о параметрах занятости [Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>Установка

Убедитесь, что установлена последняя версия Skype для бизнеса Server, а также установлено последнее исправление. Для этого сначала остановите все службы, а затем запустите установщик обновления Skype для бизнеса Server следующим образом:

1. Запустите Stop-CsWindowsService команды.

2. Запустите установщик SkypeServerUpdateInstaller.exe на каждом сервере переднего сервера в пуле.

3. Запустите установщик SkypeServerUpdateInstaller.exe на каждом сервере survivable Branch Server (SBS), если вы хотите обеспечить поддержку отбойной передачи на SBS.

Установщик развернет последнюю версию приложения "Параметры занятости". Однако приложение по умолчанию не включено. Чтобы включить приложение, выполните следующие действия:

1. Запустите [cmdlet Set-CsVoicePolicy,](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) чтобы включить параметры занятости глобально, как показано в следующем примере:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Затем, если на сайте есть политика голосовой почты, необходимо включить параметры занятости для политики голосовой почты следующим образом:

    Сначала [запустите get-CsSite,](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) чтобы получить имя сайта:

   ```powershell
   Get-CsSite
   ```

    Используйте значение Identity (например, Site:Redmond1), полученные из Get-CsSite, чтобы получить политику голосовой почты сайта следующим образом:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Если для сайта существует политика голосовой почты, запустите следующую команду:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Затем запустите cmdlet [New-CsServerApplication,](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) чтобы добавить параметры занятости в список серверных приложений, как показано в следующем примере:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Необходимо заменить %FQDN% на полное доменное имя определенного пула.

4. Затем запустите cmdlet [Update-CsAdminRole,](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) чтобы обновить роли управления доступом на основе ролей (RBAC) для параметров занятости, как показано в следующем примере:

   ```powershell
   Update-CsAdminRole
   ```

5. Наконец, запустите службы Windows Skype для бизнеса Server на всех серверах переднего сервера во всех пулах, где были установлены и включены параметры занятости, с помощью команды [Start-CsWindowsService:](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Настройка

Чтобы настроить параметры занятости, используйте [cmdlet Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Например, следующая команда настраивает параметры занятости для пользователя "Ken Myer". В этой конфигурации при любом вызове "Ken Myer" будет возвращен сигнал "занято", когда он уже находится в вызове:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

В следующем примере команда настраивает параметры занятости для пользователя Chrystal Velasquez. В этой конфигурации новые входящие вызовы на "Chrystal Velasquez" будут переададации на голосовую почту, когда она уже находится в вызове:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Сведения о конфигурации параметров занятости можно получить с помощью [cmdlet Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) В следующем примере возвращается параметр "Параметры занятости" для параметра "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Параметры занятости можно удалить с помощью [cmdlet Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) Следующая команда удаляет параметры занятости для "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Подробные сведения о cmdlets, которые используются для настройки параметров занятости, см. в техническом справочнике по [set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)

## <a name="enable-logging"></a>Включить ведение журнала

Чтобы включить ведение журнала параметров занятости с помощью службы централизованного ведения журналов, укажите следующее:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Проверка и устранение неполадок

После установки параметров занятости вы можете убедиться, что установка прошла успешно, с помощью [cmdlet Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверных приложений. Если параметры занятости установлены надлежащим образом, в выходных данных этого параметра должна быть установлена конфигурация параметров занятости следующим образом:

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

Кроме того, с помощью просмотра событий Windows можно проверить успешность установки параметров занятости и загрузку параметров занятости в Skype для бизнеса Server. To verify Busy Options, open **Event Viewer - \> Application and Services Logs - \> Skype (or Lync) Server** and search for Event ID = 30253.
