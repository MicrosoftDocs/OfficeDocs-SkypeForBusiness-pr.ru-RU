---
title: Enable Teams Rooms devices to join third-party meetings
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье рассмотрено, как настроить устройства организации и комнат Teams для поддержки сторонних собраний, присоединяемых к Cisco WebEx и Zoom.
ms.openlocfilehash: 8079b6fc231bf30a654e2513af55a806433eb83f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662364"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Позволяет устройствам комнат Teams присоединяться к сторонним собраниям

Устройства комнат Microsoft Teams поддерживают однонажатие для присоединения к собраниям по сети сторонних пользователей. Включив эту возможность, вы можете присоединиться к собраниям, которые находятся на Cisco WebEx и Zoom<sup>1,</sup> с помощью устройства комнат Teams, так же легко, как и к собраниям, которые находятся в Microsoft Teams.

Чтобы присоединиться к сторонним собраниям с устройства Teams Rooms, необходимо сделать следующее:

1. Настройка почтового ящика комнаты Exchange Online на устройстве Teams для обработки приглашений на сторонние собрания
2. Убедитесь, что в вашей организации нет политик, предотвращающих подключение к сторонним службам собраний
3. Настройка устройств с комнатами Teams для разрешение сторонних собраний

В следующих разделах покажите, как это сделать.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Шаг 1. Разрешение обработки приглашений в календарь для сторонних собраний

Прежде всего необходимо настроить правила обработки календаря для почтового ящика комнаты Exchange Online на устройстве. Почтовый ящик помещения должен разрешить внешние собрания и оставить текст сообщения и тему, чтобы видеть URL-адрес, необходимый для присоединиться к собранию сторонних экспертов. Чтобы настроить эти параметры почтового ящика помещения с помощью cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) сделайте следующее:

1. Подключите Exchange Online PowerShell. Дополнительные сведения см. в подключении к [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) с помощью базовой проверки подлинности или при подключении к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)с помощью многофакторной проверки подлинности (в зависимости от способа проверки подлинности).

2. Получите имя пользователя (UPN) почтового ящика комнаты, если не знаете его, выдав следующую команду:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. Найдите имя почтового ящика комнаты, связанного с устройством комнат Teams, и задайте его имя-имя

4. После того как вы найдете upn почтового ящика помещения, запустите следующую команду: Замените `<UserPrincipalName>` номером upn почтового ящика помещения:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Узнайте больше [об Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Шаг 2. Настройка Office 365 Threat Protection и переописывание ссылок

Чтобы обеспечить возможность перейти к собранию одним нажатием, в приглашении на собрание должна быть представлена и прочитана информация по ссылке на собрание из сторонних собраний. Если ваша организация использует функцию [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) или если вы используете стороннее решение, сканирующее все входящие и исходяющие URL-адреса на угрозы, она может изменить URL-адреса соединения собраний и сделать собрание недоступным с помощью устройства "Комнаты Teams". Чтобы этого не происходило, необходимо добавить URL-адреса сторонней службы собраний в список безопасных ссылок ATP, "не переописывать" или сторонний список исключений для переписываемого URL-адреса.

Чтобы добавить URL-адреса сторонней службы собраний в список "не переописывать" безопасные ссылки ATP, выполните действия, которые необходимо предпринять, чтобы настроить настраиваемый список URL-адресов с помощью безопасных ссылок [ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Если вы используете стороннее решение, воспользуйтесь инструкциями для этого решения, чтобы добавить URL-адреса в список исключений для переписываемого URL-адреса.

Вот несколько записей, которые может потребоваться добавить в список "не переописывать" безопасные ссылки ATP или сторонний список исключений с переописью URL-адресов:

- **Cisco WebEx**`*.webex.com*`
- **"Масштаб",** `*.zoom.us*` `*.zoom.com*``*.zoomgov.com*`

Чтобы получить полный список URL-адресов, которые нужно добавить в список безопасных ссылок ATP, не переописывайте список исключений или переописывание url-адресов сторонних поставщиков, обратитесь к стороннему поставщику услуг собраний, от который вы хотите принять приглашения на собрания. 

> [!CAUTION]
> Добавляйте только url-адреса, которые вы доверяете, в список надежных ссылок ATP, "не переописывайте" список исключений или список исключений с переописью URL-адреса сторонних компаний.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Шаг 3. Включить сторонние собрания на устройстве

Последний шаг, который необходимо сделать, — разрешить каждому устройству Teams Rooms присоединяться к сторонним собраниям. Для сторонних собраний требуется имя пользователя и адрес электронной почты, чтобы присоединиться к ним. Если имя пользователя и адрес электронной почты, которые вам нужно использовать, отличаются от почтовых ящиков в комнате устройства, их необходимо добавить на устройство. Это можно сделать в параметрах устройства или в XML-файле config.

### <a name="use-device-settings"></a>Использование параметров устройства

Чтобы настроить устройство Teams Rooms с помощью сенсорного экрана, сделайте следующее:

1. На устройстве комнат Microsoft Teams выберите **"Еще...**
2. Выберите **"Параметры",** а затем введите имя пользователя и пароль администратора устройства.
3. Перейдите на **вкладку "Собрания"** и выберите **Cisco WebEx,** **Zoom**<sup>1</sup>или оба
4. Если вы хотите присоединиться к собранию с помощью имени пользователя и адреса электронной почты, связанных с почтовым ящиком комнаты, выберите "Присоединиться с **данными о помещении"**
5. Если вы хотите присоединиться к собранию с альтернативным имем и адресом электронной почты, выберите **"Присоединиться** с использованием настраиваемой информации" и введите имя пользователя и адрес электронной почты, которые вы хотите использовать.
6. Выберите **"Сохранить и выйти".** Ваше устройство перезапустится.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Использование файла SkypeSettings.xml конфигурации

К файлу, находящегося в папке, можно добавить `SkypeSettings.xml` следующие `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` параметры: Дополнительные сведения о файле см. в файле конфигурации XML для удаленного управления настройками консоли в комнатах `SkypeSettings.xml` [Microsoft Teams.](xml-config-file.md)

Чтобы включить собрания Cisco WebEx, установите `WebExMeetingsEnabled` для XML-элемента true (истина), как поется в этом примере. 

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Чтобы включить собрания с о<sup>масштабом 1,</sup> установите для XML-элемента true `ZoomMeetingsEnabled` (истина), как поется в этом примере. 

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

При желании вы можете указать пользовательское имя пользователя и адрес электронной почты, чтобы присоединяться к собраниям сторонних пользователей, используя следующие XML-элементы: Если вы предоставите не допустимые значения, на устройстве teams Rooms по умолчанию будут использовать имя пользователя и адрес электронной почты почтового ящика помещения.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Чтобы присоединиться к собранию Cisco WebEx с устройства комнат Teams, собрание Cisco необходимо проводить с помощью веб-приложения Cisco WebEx версии WBS 40.7 или более поздней.

<sup>1 Присоединение</sup> к собраниям с масштабом в настоящее время доступно только для выбора клиентов комнат Microsoft Teams с помощью программы доступа к технологии (TAP).
