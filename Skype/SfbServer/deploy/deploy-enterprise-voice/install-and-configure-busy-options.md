---
title: Установка и настройка параметров занятости для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.
ms.openlocfilehash: 5e0dde157fc39ab7c24ddd297e858ce5a06e888f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835917"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Установка и настройка параметров занятости для Skype для бизнеса Server

Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.

Busy Options — это новая голосовая политика, введенная в накопительном обновлении за июль 2016 г., которая позволяет настроить обработку входящих вызовов, когда пользователь уже находится на вызове или конференции или приостановил вызов. Новые или входящие вызовы можно отклонить с помощью занятого сигнала или отправить на голосовую почту.

Если в организации включены параметры занятости, все пользователи Enterprise, как Корпоративная голосовая связь, так и Корпоративная голосовая связь, могут использовать следующие параметры конфигурации:

- Занят на busy - в котором новые входящие вызовы будут отклонены с занят сигналом, если пользователь занят.

- Голосовая почта в Busy — в которой новые входящие вызовы будут перенаад- в голосовую почту, если пользователь занят.

Независимо от того, как настраиваются их параметры занятости, пользователям на вызове или конференции или при удержании не мешает инициировать новые вызовы или конференции.

Дополнительные сведения о функции Busy Options см. в меню [Plan for Busy Options for Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>Установка

Убедитесь, что установлена последняя Skype для бизнеса Server установлена последняя версия исправлений. Для этого сначала остановите все службы, а затем выполните установку Skype для бизнеса Server обновления следующим образом:

1. Запустите Stop-CsWindowsService команду.

2. Запустите SkypeServerUpdateInstaller.exe установки на каждом переднем сервере в пуле.

3. Запустите SkypeServerUpdateInstaller.exe установщика на каждом выживаемом сервере филиала (SBS), если вы хотите обеспечить поддержку при сбойе на SBS.

Установщик развернет последнюю версию приложения Busy Options. Однако по умолчанию приложение не включено. Чтобы включить приложение, выполните следующие действия:

1. Запустите [комлет Set-CsVoicePolicy,](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) чтобы глобально включить параметры занятости, как показано в следующем примере:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Далее, если на сайте имеется голосовая политика, необходимо включить параметры занятости для голосовой политики следующим образом:

    Сначала [запустите Get-CsSite,](/powershell/module/skype/get-cssite?view=skype-ps) чтобы получить имя сайта:

   ```powershell
   Get-CsSite
   ```

    Используйте значение Identity (например: Site:Redmond1), извлеченный из Get-CsSite, чтобы получить голосовую политику сайта следующим образом:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Если для сайта существует голосовая политика, запустите следующую команду:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Далее запустите комлет [New-CsServerApplication,](/powershell/module/skype/new-csserverapplication?view=skype-ps) чтобы добавить параметры занятости в список серверных приложений, как показано в следующем примере:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Необходимо заменить %FQDN% полностью квалифицированным доменным именем определенного пула.

4. Далее запустите комлет [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) для обновления ролей управления доступом (RBAC) для cmdlets Busy Options, как показано в следующем примере:

   ```powershell
   Update-CsAdminRole
   ```

5. Наконец, запустите службы Skype для бизнеса Server Windows на всех серверах переднего конца во всех пулах, где были установлены и включены параметры занятости, с помощью команды [Start-CsWindowsService:](/powershell/module/skype/start-cswindowsservice?view=skype-ps)

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configure (Настроить)

Чтобы настроить параметры занятости, используйте [комлет Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Например, следующая команда настраивает параметры занятости для пользователя "Ken Myer". В этой конфигурации любой вызов "Ken Myer" возвращает сигнал занятости, когда он уже находится в вызове:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

В следующем примере команда настраивает параметры занятости для пользователя "Chrystal Velasquez". В этой конфигурации новые входящие вызовы в "Chrystal Velasquez" будут пересылаться на голосовую почту, когда она уже находится в вызове:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Сведения о параметрах занятости можно получить с помощью [cmdlet Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) В следующем примере возвращается параметр Busy Options для "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Вы можете удалить параметры занятости с помощью [cmdlet Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) Следующая команда удаляет параметры занятости для "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Подробные сведения о cmdlets, которые вы используете для настройки Параметры занятости, см. в техническом справочном контенте [для Set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Включить ведение журнала

Чтобы включить ведение журнала для параметров занятости с помощью централизированной службы ведения журнала, укажите следующее:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Проверка и устранение неполадок

После установки Параметры занятости можно убедиться, что установка была успешной с помощью [cmdlet Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверных приложений. Если параметры занятости установлены надлежащим образом, то в выходе этого комлета должна быть установлена конфигурация "Параметры занятости" следующим образом:

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

Вы также можете Windows просмотра событий, чтобы убедиться, что установка Busy Options была успешной и что Skype для бизнеса Server загружены параметры занятости. Чтобы проверить параметры занятости, откройте журналы просмотра событий — журналы приложений и **\> служб — Skype \> (или Lync) Server** и поиск по ID события = 30253.