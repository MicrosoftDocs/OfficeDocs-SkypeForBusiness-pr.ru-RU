---
title: Установка и Настройка параметров занятости в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 5078041401c710a249470ed6d3871f38a98a7420
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113122"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Установка и Настройка параметров занятости в Skype для бизнеса Server

Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.

Параметры занятости — это новая политика голосовой связи, появившаяся в накопительном пакете обновления 2016 за Июль, которая позволяет настроить способ обработки входящих вызовов, когда пользователь уже находился в вызове или в конференции, или вызов заблокирован. Новые или входящие звонки могут отклоняться с помощью сигнала "занято" или пересылки на голосовую почту.

Если для организации включены параметры занятости, все пользователи на предприятии, как для корпоративной голосовой связи, так и для пользователей, не являющихся корпоративными, могут использовать следующие параметры конфигурации:

- Занято при занятости, при котором новые входящие звонки отклоняются с сигналом занятости, если пользователь занят.

- Голосовая почта (при занятости), при которой новые входящие звонки будут перенаправляться на голосовую почту, если пользователь занят.

Независимо от того, как настроены параметры занятости, пользователи в вызове или конференции, а также при вызове на удержание не могут инициировать новые вызовы или конференции.

Дополнительные сведения о функции "занято" можно найти в статье [Планирование возможностей занятости в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Установка

Убедитесь, что установлена последняя версия Skype для бизнеса Server и вы установили Последнее исправление. Для этого сначала остановите все службы, а затем запустите установщик обновлений Skype для бизнеса Server следующим образом:

1. Выполните команду Stop – CsWindowsService.

2. Запустите установщик файл skypeserverupdateinstaller. exe на каждом сервере переднего плана в пуле.

3. Запустите установщик файл skypeserverupdateinstaller. exe на каждом сервере для обеспечения связи в филиалах (SBS), если вы хотите обеспечить поддержку отработки отказа в SBS.

Установщик будет развертывать последнюю версию приложения "занято". Однако приложение по умолчанию отключено. Чтобы включить приложение, выполните следующие действия:

1. Выполните командлет [Set – CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) для глобального включения параметров занятости, как показано в следующем примере:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. После этого, если на сайте имеется политика голосовой связи, необходимо включить параметры занятости для политики голосовой связи следующим образом.

    Сначала выполните командлет [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) , чтобы получить имя сайта:

   ```powershell
   Get-CsSite
   ```

    Используйте значение идентификатора (например: site: Redmond1), полученное из Get-CsSite, чтобы получить политику голосовой связи для сайта следующим образом:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Если для сайта существует политика голосовой связи, выполните следующую команду:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Затем выполните командлет [New – CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , чтобы добавить параметры занятости в список серверных приложений, как показано в следующем примере:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Необходимо заменить% FQDN% на полное доменное имя определенного пула.

4. Затем выполните командлет [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) , чтобы обновить роли управления доступом на основе РОЛЕЙ (RBAC) для командлетов параметров занятости, как показано в следующем примере:

   ```powershell
   Update-CsAdminRole
   ```

5. Наконец, запустите службы Windows Skype для бизнеса Server на всех серверах переднего плана во всех пулах, где были установлены и включены параметры занятости, выполнив команду [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configure (Настроить)

Чтобы настроить параметры занятости, используйте командлет [Set – CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Например, следующая команда настраивает параметры занятости для пользователя "Ken Myer". В этой конфигурации любой вызов "Ken Myer" возвратит сигнал занятости, когда он уже находился в вызове:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

В следующем примере команда настраивает параметры занятости для пользователя "Чристал переадресуются". В этой конфигурации новые входящие вызовы "Чристал переадресуются" будут пересылаться в голосовую почту, когда она уже находится в вызове:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Сведения о конфигурации для параметров занятости можно получить с помощью командлета [Get – CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . В следующем примере возвращаются параметры занятости для "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Параметры занятости можно удалить с помощью командлета [Remove – CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . Следующая команда удаляет параметры занятости для "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Подробные сведения о командлетах, используемых для настройки параметров занятости, приведены в статье справочные материалы по командлетам [Set — CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get/CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove/CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Включение ведения журнала

Чтобы включить ведение журнала для параметров занятости с помощью централизованной службы ведения журналов, укажите следующее:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Проверка и устранение неполадок

После установки параметров занятости можно убедиться, что установка прошла успешно, с помощью командлета [Get – CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверных приложений. Если параметры занятости установлены правильно, выходные данные командлета должны показывать конфигурацию "занято", как показано ниже.

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

Кроме того, с помощью средства просмотра событий Windows можно проверить успешность установки параметров занятости и успешной загрузки Skype для бизнеса Server. Чтобы проверить параметры занятости, откройте **окно просмотра событий\> — журналы приложений и служб\> — Skype (или Lync) Server** и выполните поиск по идентификатору события 30253.
