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
localization_priority: Normal
description: В этой статье обсуждается настройка организации и Комнаты Teams устройств для поддержки присоединения к собраниям сторонних разработчиков в Cisco WebEx и Zoom.
ms.openlocfilehash: ef14d1f342c6f2b34ad7c948a2688fa39a09801d
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796693"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="2bced-103">Enable Teams Room devices to join third-party meetings</span><span class="sxs-lookup"><span data-stu-id="2bced-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="2bced-104">Комнаты Microsoft Teams устройства поддерживают сенсорный экран для присоединения к собраниям по сети сторонних пользователей, которые также называются Прямым гостевом присоединением.</span><span class="sxs-lookup"><span data-stu-id="2bced-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="2bced-105">Если включена, вы можете использовать устройство Комнаты Teams, чтобы присоединяться к собраниям Cisco WebEx и Масштаб так же легко, как и к собраниям, которые Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2bced-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="2bced-106">Прежде чем присоединяться к собраниям сторонних Комнаты Teams устройстве, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="2bced-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="2bced-107">Настройте почтовый Комнаты Teams на Exchange Online устройства для обработки приглашений на собрания сторонних людей.</span><span class="sxs-lookup"><span data-stu-id="2bced-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="2bced-108">Убедитесь, что в вашей организации нет политик, которые бы препятствовали подключению к сторонним службам собраний.</span><span class="sxs-lookup"><span data-stu-id="2bced-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="2bced-109">Настройте свои Комнаты Teams, чтобы разрешить собрания сторонних пользователей.</span><span class="sxs-lookup"><span data-stu-id="2bced-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="2bced-110">В следующих разделах покажите, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="2bced-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="2bced-111">Шаг 1. Разрешение обработки приглашений в календарь для сторонних собраний</span><span class="sxs-lookup"><span data-stu-id="2bced-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="2bced-112">Первое, что необходимо сделать, чтобы включить однонажатие на устройстве с комнатами группы, — настроить правила обработки календаря для почтового ящика Exchange Online комнаты.</span><span class="sxs-lookup"><span data-stu-id="2bced-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="2bced-113">Почтовый ящик помещения должен разрешить внешние собрания и сохранить текст сообщения и тему, чтобы видеть URL-адрес, необходимый для присоединиться к собранию сторон.</span><span class="sxs-lookup"><span data-stu-id="2bced-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="2bced-114">Чтобы настроить эти параметры почтового ящика помещения с помощью cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2bced-114">To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="2bced-115">Подключение Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bced-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="2bced-116">Дополнительные сведения см. в Подключение в [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) с базовой проверкой подлинности или Подключение в [Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)с помощью многофакторной проверки подлинности в зависимости от метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2bced-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="2bced-117">Если вы не знаете имя директора-пользователя для почтового ящика комнаты, вы можете получить его, выдав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2bced-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="2bced-118">Найдите имя почтового ящика комнаты, связанного с устройством Комнаты Teams, и задайте его имя-имя.</span><span class="sxs-lookup"><span data-stu-id="2bced-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="2bced-119">После того как вы найдете имени и имени почтового ящика помещения, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2bced-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="2bced-120">Замените `<UserPrincipalName>` номером upN почтового ящика помещения:</span><span class="sxs-lookup"><span data-stu-id="2bced-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="2bced-121">Подробнее о Exchange Online [PowerShell.](/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="2bced-121">Learn more about [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="2bced-122">Шаг 2. Настройка Office 365 Threat Protection и переописывание ссылок</span><span class="sxs-lookup"><span data-stu-id="2bced-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="2bced-123">Чтобы можно было присоединиться одним касанием, в приглашении на собрание должны быть представлены и прочитаны ссылки на ссылки на собрание из сторонних собраний.</span><span class="sxs-lookup"><span data-stu-id="2bced-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="2bced-124">Если в вашей организации используется функция [Office 365 Advanced Threat Protection Сейф Links](/microsoft-365/security/office-365-security/atp-safe-links) или вы используете стороннее решение, проверяющее все входящие и исходяющие URL-адреса на угрозы, это может привести к изменению URL-адресов для пользования собранием и сделать собрание неизменяемым с помощью устройства Комнаты Teams.</span><span class="sxs-lookup"><span data-stu-id="2bced-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="2bced-125">Чтобы этого не происходило, необходимо добавить URL-адреса сторонней службы собраний в список url-адресов ATP Сейф Ссылки "не переописывать" или список исключений для стороннего URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="2bced-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="2bced-126">Чтобы добавить URL-адреса службы сторонних собраний в список ATP Сейф Ссылки "не переописывать", выполните действия, которые можно найти в списке Настройка пользовательского списка URL-адресов с помощью ссылок на Сейф [ATP.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="2bced-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="2bced-127">Если вы используете стороннее решение, воспользуйтесь инструкциями для этого решения, чтобы добавить URL-адреса в список исключений для переописи URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="2bced-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="2bced-128">Вот несколько записей, которые может потребоваться добавить в список исключений atP Сейф Ссылки "не переописывать" или список исключений для сторонний URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="2bced-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="2bced-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="2bced-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="2bced-130">**"Масштаб"** `*.zoom.us*` `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="2bced-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="2bced-131">Чтобы получить полный список URL-адресов для добавления в список atp Сейф Ссылки "не переописывать" или список исключений для переописываемого URL-адреса стороннего поставщика, обратитесь к стороннему поставщику услуг собраний, от который вы хотите принять приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="2bced-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="2bced-132">Добавьте только URL-адреса, которые вы доверяете списку Сейф ATP: ссылки "не переописывать" списки исключений или списки исключений для стороннего URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="2bced-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="2bced-133">Шаг 3. Включить сторонние собрания на устройстве</span><span class="sxs-lookup"><span data-stu-id="2bced-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="2bced-134">Последнее, что необходимо сделать, — разрешить каждому устройству Комнаты Teams присоединяться к собраниям сторонних сторон.</span><span class="sxs-lookup"><span data-stu-id="2bced-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="2bced-135">Для собраний сторонних пользователей требуется имя пользователя и адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2bced-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="2bced-136">Если имя пользователя и адрес электронной почты, которые вам нужно использовать, отличаются от почтовых ящиков комнат на устройстве, их необходимо добавить на устройство.</span><span class="sxs-lookup"><span data-stu-id="2bced-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="2bced-137">Это можно сделать в параметрах устройства или в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="2bced-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="2bced-138">Использование параметров устройства</span><span class="sxs-lookup"><span data-stu-id="2bced-138">Use device settings</span></span>

<span data-ttu-id="2bced-139">Чтобы настроить устройство Комнаты Teams с помощью сенсорного экрана, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2bced-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="2bced-140">На устройстве Комнаты Microsoft Teams еще **...**.</span><span class="sxs-lookup"><span data-stu-id="2bced-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="2bced-141">Выберите **Параметры**, а затем введите имя пользователя и пароль администратора устройства.</span><span class="sxs-lookup"><span data-stu-id="2bced-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="2bced-142">Перейдите на **вкладку Собрания** и выберите **Cisco WebEx**, **Масштаб** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="2bced-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="2bced-143">Если вы хотите присоединиться к собранию с иным имем пользователя и адресом электронной почты, связанным с почтовым ящиком комнаты, выберите Присоединиться с **информацией о помещении**.</span><span class="sxs-lookup"><span data-stu-id="2bced-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="2bced-144">Если вы хотите присоединиться к собранию с альтернативным  иным имем пользователя и адресом электронной почты, выберите Присоединиться с настраиваемой информацией и введите имя пользователя и адрес электронной почты, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="2bced-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="2bced-145">Выберите **Сохранить и выйти**.</span><span class="sxs-lookup"><span data-stu-id="2bced-145">Select **Save and exit**.</span></span> <span data-ttu-id="2bced-146">Устройство перезапустится.</span><span class="sxs-lookup"><span data-stu-id="2bced-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="2bced-147">Использование файла SkypeSettings.xml конфигурации</span><span class="sxs-lookup"><span data-stu-id="2bced-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="2bced-148">К файлу, находящегося в папке , можно добавить `SkypeSettings.xml` следующие `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` параметры:</span><span class="sxs-lookup"><span data-stu-id="2bced-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="2bced-149">Дополнительные сведения о файле см. в Комнаты Microsoft Teams удаленного управления настройками консоли с помощью `SkypeSettings.xml` [XML-файла конфигурации.](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="2bced-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="2bced-150">Чтобы включить собрания Cisco WebEx, за установите для XML-элемента true `WebExMeetingsEnabled` (Истина) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2bced-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="2bced-151">Чтобы включить масштабирование собраний, за установите `ZoomMeetingsEnabled` для XML-элемента true (Истина) следующим образом. </span><span class="sxs-lookup"><span data-stu-id="2bced-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="2bced-152">При желании вы можете указать пользовательское имя пользователя и адрес электронной почты, чтобы присоединяться к собраниям сторонних пользователей с помощью следующих XML-элементов:</span><span class="sxs-lookup"><span data-stu-id="2bced-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="2bced-153">Если вы предоставите не допустимые значения, на Комнаты Teams будет по умолчанию использовать имя пользователя и адрес электронной почты почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="2bced-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="2bced-154">Чтобы присоединиться к собранию Cisco WebEx с устройства Комнаты Teams, собрание Cisco должно быть организовано в приложении WebEx Meetings Pro с помощью веб-приложения Cisco WebEx версии WBS 40.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="2bced-154">To join a Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted in WebEx Meetings Pro using Cisco WebEx web application version WBS 40.7 or later.</span></span> 
