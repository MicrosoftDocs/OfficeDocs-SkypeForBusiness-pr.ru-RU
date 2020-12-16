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
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682388"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="49426-103">Возможность перейти к собраниям сторонних пользователей с помощью устройств комнат Teams</span><span class="sxs-lookup"><span data-stu-id="49426-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="49426-104">Устройства комнат Microsoft Teams поддерживают однонажатие для присоединения к сторонним собраниям по сети, которые также называются прямым гостевом присоединением.</span><span class="sxs-lookup"><span data-stu-id="49426-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="49426-105">Если включена возможность, вы можете использовать устройство комнат Teams, чтобы присоединиться к собраниям, которые находятся на Cisco WebEx и изменить масштаб, так же легко, как и к собраниям, которые находятся в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49426-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="49426-106">Чтобы присоединиться к сторонним собраниям с устройства Teams Rooms, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="49426-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="49426-107">Настройте почтовый ящик комнат Exchange Online на устройстве Teams для обработки приглашений на сторонние собрания.</span><span class="sxs-lookup"><span data-stu-id="49426-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="49426-108">Убедитесь, что в вашей организации нет политик, предотвращающих подключение к сторонним службам собраний.</span><span class="sxs-lookup"><span data-stu-id="49426-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="49426-109">Настройте устройства комнат Teams, чтобы разрешить сторонние собрания.</span><span class="sxs-lookup"><span data-stu-id="49426-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="49426-110">В следующих разделах покажите, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="49426-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="49426-111">Шаг 1. Разрешение обработки приглашений в календарь для сторонних собраний</span><span class="sxs-lookup"><span data-stu-id="49426-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="49426-112">Прежде всего необходимо настроить правила обработки календаря для почтового ящика комнаты Exchange Online на устройстве.</span><span class="sxs-lookup"><span data-stu-id="49426-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="49426-113">Почтовый ящик помещения должен разрешить внешние собрания и оставить текст сообщения и тему, чтобы видеть URL-адрес, необходимый для присоединиться к собранию сторонних экспертов.</span><span class="sxs-lookup"><span data-stu-id="49426-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="49426-114">Чтобы настроить эти параметры почтового ящика помещения с помощью cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="49426-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="49426-115">Подключите Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49426-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="49426-116">Дополнительные сведения см. в видео "Подключение к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) с помощью базовой проверки подлинности" или "Подключение к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)с помощью многофакторной проверки подлинности в зависимости от метода проверки подлинности".</span><span class="sxs-lookup"><span data-stu-id="49426-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="49426-117">Получите имя пользователя (upN) почтового ящика комнаты, если вы не знаете его, выдав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="49426-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="49426-118">Найдите имя почтового ящика комнаты, связанного с вашим устройством комнат Teams, и задайте его имя-имя.'</span><span class="sxs-lookup"><span data-stu-id="49426-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="49426-119">После того как вы найдете имени имени электронной почты почтового ящика помещения, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="49426-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="49426-120">Замените `<UserPrincipalName>` номером upn почтового ящика помещения:</span><span class="sxs-lookup"><span data-stu-id="49426-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="49426-121">Узнайте больше [об Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="49426-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="49426-122">Шаг 2. Настройка Office 365 Threat Protection и переописывание ссылок</span><span class="sxs-lookup"><span data-stu-id="49426-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="49426-123">Чтобы обеспечить возможность присоединиться одним нажатием, сведения о ссылке на собрание из стороннее собрание должны быть представлены и прочитаны в приглашении на собрание.</span><span class="sxs-lookup"><span data-stu-id="49426-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="49426-124">Если ваша организация использует функцию [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) или если вы используете стороннее решение, сканирующее все входящие и исходяющие URL-адреса на угрозы, она может изменить URL-адреса соединения собраний и сделать собрание недоступным с помощью устройства "Комнаты Teams".</span><span class="sxs-lookup"><span data-stu-id="49426-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="49426-125">Чтобы этого не происходило, необходимо добавить URL-адреса сторонней службы собраний в список безопасных ссылок ATP, "не переописывать" или сторонний список исключений при переописи URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="49426-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="49426-126">Чтобы добавить URL-адреса сторонней службы собраний в список "не переописывать" безопасные ссылки ATP, выполните действия, которые необходимо предпринять, чтобы настроить настраиваемый список URL-адресов с помощью безопасных ссылок [ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="49426-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="49426-127">Если вы используете стороннее решение, воспользуйтесь инструкциями для этого решения, чтобы добавить URL-адреса в список исключений для переписываемого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="49426-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="49426-128">Вот несколько записей, которые может потребоваться добавить в список "не переописывать" безопасные ссылки ATP или сторонний список исключений с переописью URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="49426-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="49426-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="49426-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="49426-130">**"Масштаб",** `*.zoom.us*` `*.zoom.com*``*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="49426-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="49426-131">Чтобы получить полный список URL-адресов для добавления в список безопасных ссылок ATP, не переописывайте их, обратитесь к стороннему поставщику услуг собраний, от который вы хотите принять приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="49426-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="49426-132">Добавляйте только url-адреса, которые вы доверяете, в список надежных ссылок ATP, "не переописывайте" список исключений или список исключений с переописью URL-адреса сторонних компаний.</span><span class="sxs-lookup"><span data-stu-id="49426-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="49426-133">Шаг 3. Включить сторонние собрания на устройстве</span><span class="sxs-lookup"><span data-stu-id="49426-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="49426-134">Последний шаг, который необходимо сделать, — разрешить каждому устройству Teams Rooms присоединяться к сторонним собраниям.</span><span class="sxs-lookup"><span data-stu-id="49426-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="49426-135">Сторонним собраниям требуется имя пользователя и адрес электронной почты, чтобы присоединиться к ним.</span><span class="sxs-lookup"><span data-stu-id="49426-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="49426-136">Если имя пользователя и адрес электронной почты, которые вам нужно использовать, отличаются от почтовых ящиков в комнате устройства, их необходимо добавить на устройство.</span><span class="sxs-lookup"><span data-stu-id="49426-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="49426-137">Это можно сделать в параметрах устройства или в XML-файле config.</span><span class="sxs-lookup"><span data-stu-id="49426-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="49426-138">Использование параметров устройства</span><span class="sxs-lookup"><span data-stu-id="49426-138">Use device settings</span></span>

<span data-ttu-id="49426-139">Чтобы настроить устройство teams Rooms с помощью сенсорного экрана, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="49426-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="49426-140">На устройстве комнат Microsoft Teams выберите **"Еще...".**</span><span class="sxs-lookup"><span data-stu-id="49426-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="49426-141">Выберите **"Параметры"** и введите имя пользователя и пароль администратора устройства.</span><span class="sxs-lookup"><span data-stu-id="49426-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="49426-142">Перейдите на **вкладку "Собрания"** и выберите **Cisco WebEx,** **Zoom** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="49426-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="49426-143">Если вы хотите присоединиться к собранию с помощью имени пользователя и адреса электронной почты, связанных с почтовым ящиком комнаты, выберите "Присоединиться с **данными о помещении".**</span><span class="sxs-lookup"><span data-stu-id="49426-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="49426-144">Если вы хотите присоединиться к собранию с альтернативным имем пользователя и адресом электронной почты, выберите **"Присоединиться** с использованием настраиваемой информации" и введите имя пользователя и адрес электронной почты, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="49426-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="49426-145">Выберите **"Сохранить и выйти".**</span><span class="sxs-lookup"><span data-stu-id="49426-145">Select **Save and exit**.</span></span> <span data-ttu-id="49426-146">Ваше устройство перезапустится.</span><span class="sxs-lookup"><span data-stu-id="49426-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="49426-147">Использование файла SkypeSettings.xml конфигурации</span><span class="sxs-lookup"><span data-stu-id="49426-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="49426-148">К файлу, находящегося в папке, можно добавить `SkypeSettings.xml` следующие `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` параметры:</span><span class="sxs-lookup"><span data-stu-id="49426-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="49426-149">Дополнительные сведения о файле см. в файле конфигурации XML для удаленного управления настройками консоли комнат `SkypeSettings.xml` [Microsoft Teams.](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="49426-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="49426-150">Чтобы включить собрания Cisco WebEx, установите `WebExMeetingsEnabled` для XML-элемента true (истина), как поется в этом примере. </span><span class="sxs-lookup"><span data-stu-id="49426-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="49426-151">Чтобы включить собрания с о масштабированием, установите `ZoomMeetingsEnabled` для XML-элемента true (истина), как поется в этом примере. </span><span class="sxs-lookup"><span data-stu-id="49426-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="49426-152">При желании вы можете указать пользовательское имя пользователя и адрес электронной почты, чтобы присоединяться к собраниям сторонних пользователей, используя следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="49426-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="49426-153">Если вы предоставите не действительные значения, на устройстве "Комнаты Teams" по умолчанию будут использовать имя пользователя и адрес электронной почты почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="49426-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="49426-154">Чтобы присоединиться к собранию Cisco WebEx с устройства комнат Teams, собрание Cisco необходимо проводить с помощью веб-приложения Cisco WebEx версии WBS 40.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="49426-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

