---
title: Enable Комнаты Teams devices to join third-party meetings
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
ms.localizationpriority: medium
description: В этой статье рассмотрено, как настроить организацию и устройства Комнаты Teams для поддержки присоединения к собраниям сторонних разработчиков в Cisco WebEx и Zoom.
ms.openlocfilehash: d952df95a396e29ffcf393ded068a30459707218
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015249"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Enable Teams Room devices to join third-party meetings

Комнаты Microsoft Teams поддерживают сенсорный экран для присоединения к собраниям по сети сторонних пользователей, которые также называются Direct Guest Join. Если она включена, Комнаты Teams присоединиться к собраниям, которые будут проводиться в Cisco WebEx и Масштабе, так же легко, как и к собраниям, которые Microsoft Teams.

Прежде чем присоединяться к собраниям сторонних Комнаты Teams, необходимо сделать следующее:

1. Настройте почтовый Комнаты Teams комнаты Exchange Online для обработки приглашений на собрания сторонних людей.
2. Убедитесь, что в вашей организации нет политик, которые бы препятствовали подключению к сторонним службам собраний.
3. Настройте Комнаты Teams разрешить сторонние собрания.

В следующих разделах покажите, как это сделать.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Шаг 1. Разрешение обработки приглашений в календарь для сторонних собраний

Первое, что необходимо сделать, чтобы включить однонажатие присоединиться из комнаты группы, — настроить правила обработки календаря для почтового ящика Exchange Online помещения устройства. Почтовый ящик помещения должен разрешить внешние собрания и сохранить текст сообщения и тему, чтобы видеть URL-адрес, необходимый для присоединиться к собранию сторон. Чтобы настроить эти параметры почтового ящика помещения с помощью cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) сделайте следующее:

1. Подключение Exchange Online PowerShell. Дополнительные сведения см. в Подключение в [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) с базовой проверкой подлинности или Подключение в [Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)с помощью многофакторной проверки подлинности в зависимости от метода проверки подлинности.

2. Если вы не знаете имя директора-пользователя для почтового ящика комнаты, вы можете получить его, выдав следующую команду:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Найдите имя почтового ящика комнаты, связанного с устройством Комнаты Teams, и задайте его имя-имя.

4. После того как вы найдете имени или имени почтового ящика помещения, запустите следующую команду: Замените `<UserPrincipalName>` номером upN почтового ящика помещения:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Подробнее о Exchange Online [PowerShell.](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Шаг 2. Настройка Office 365 Threat Protection и переописывание ссылок

Чтобы можно было присоединиться одним касанием, сведения о ссылке на собрание из стороннее собрание должны быть представлены и прочитаны в приглашении на собрание. Если в вашей организации используется функция [ссылок Office 365 Advanced Threat Protection Сейф или](/microsoft-365/security/office-365-security/atp-safe-links) вы используете стороннее решение, проверяющее все входящие и исходяющие URL-адреса на угрозы, это может привести к изменению URL-адресов присоединиться к собранию и сделать собрание неузнаваемым с помощью устройства Комнаты Teams. Чтобы этого не происходило, необходимо добавить URL-адреса сторонней службы собраний в список url-адресов ATP Сейф Ссылки "не переописывать" или список исключений для стороннего URL-адреса.

Чтобы добавить URL-адреса сторонней службы собраний в список ATP Сейф Ссылки "не переописывать", выполните действия, которые можно найти в списке Настройка пользовательского списка URL-адресов с помощью ссылок на Сейф [ATP.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Если вы используете стороннее решение, воспользуйтесь инструкциями для этого решения, чтобы добавить URL-адреса в список исключений для переописи URL-адресов.

Вот несколько записей, которые может потребоваться добавить в список исключений atP Сейф Ссылки "не переописывать" или список исключений для сторонний URL-адресов:

- **Cisco WebEx** `*.webex.com*`
- **"Масштаб"** `*.zoom.us*` `*.zoom.com*` , `*.zoomgov.com*`

Чтобы получить полный список URL-адресов для добавления в список ATP Сейф Ссылки "не переописывать" или список исключений для переописываемого URL-адреса стороннего поставщика, обратитесь к стороннему поставщику услуг собраний, от который вы хотите принять приглашения на собрания. 

> [!CAUTION]
> Добавьте только URL-адреса, которые вы доверяете списку Сейф ATP: ссылки "не переописывайте" список исключений или список исключений для стороннего URL-адреса.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Шаг 3. Включить сторонние собрания на Комнаты Teams

Последнее, что необходимо сделать, — Комнаты Teams присоединяться к собраниям сторонних сторон. Для собраний сторонних пользователей требуется имя пользователя и адрес электронной почты. Если имя пользователя и адрес электронной почты, которые вам нужно использовать, отличаются от почтовых ящиков комнат устройства, их необходимо добавить на устройство. Это можно сделать в параметрах Комнаты Teams или в XML-файле.

### <a name="use-device-settings"></a>Использование параметров устройства

Чтобы настроить Комнаты Teams с помощью консоли с сенсорным экраном, сделайте следующее:

1. На консоли Комнаты Microsoft Teams выберите **Еще ...**.
2. Выберите **Параметры**, а затем введите имя пользователя и пароль администратора устройства.
3. Перейдите на **вкладку Собрания** и выберите **Cisco WebEx**, **Масштаб** или и то, и другое.
4. Если вы хотите присоединиться к собранию с помощью имени пользователя и адреса электронной почты, связанных с почтовым ящиком комнаты, выберите Присоединиться с **информацией о помещении**.
5. Если вы хотите присоединиться к собранию с другим иным имем пользователя и адресом электронной почты, выберите Присоединиться с настраиваемой информацией и введите имя пользователя и адрес электронной почты, которые вы хотите использовать. 
6. Выберите **Сохранить и выйти**. Ваше устройство перезапустится.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Использование файла SkypeSettings.xml конфигурации

К файлу, находящегося в папке , можно добавить `SkypeSettings.xml` следующие `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` параметры: Дополнительные сведения о файле см. в Комнаты Microsoft Teams удаленного управления настройками консоли с помощью `SkypeSettings.xml` [XML-файла конфигурации.](xml-config-file.md)

Чтобы включить собрания Cisco WebEx, за установите для XML-элемента true `WebExMeetingsEnabled` (Истина) следующим образом.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Чтобы включить масштабирование собраний, за установите `ZoomMeetingsEnabled` для XML-элемента true (Истина) следующим образом. 

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

При желании вы можете указать пользовательское имя пользователя и адрес электронной почты, чтобы присоединяться к собраниям сторонних пользователей с помощью следующих XML-элементов: Если вы предоставите не допустимые значения, на Комнаты Teams будет по умолчанию использовать имя пользователя и адрес электронной почты почтового ящика помещения.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Чтобы присоединиться к собранию Cisco WebEx с устройства Комнаты Teams, собрание Cisco должно быть организовано в приложении WebEx Meetings Pro с помощью веб-приложения Cisco WebEx версии WBS 40.7 или более поздней. 
