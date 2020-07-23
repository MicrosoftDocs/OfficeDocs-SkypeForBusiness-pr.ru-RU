---
title: Включение и использование устройствами рабочих комнат для присоединения к собраниям третьих лиц
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
description: В этой статье рассказывается о том, как настроить организацию и использование устройствами в рабочих группах для поддержки собраний третьих лиц, присоединяющихся к Cisco WebEx и масштабу.
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372218"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="f8017-103">Включение и использование устройствами из комнаты для присоединения к собраниям сторонних разработчиков</span><span class="sxs-lookup"><span data-stu-id="f8017-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="f8017-104">В Microsoft Teams устройства поддерживают один сенсорный интерфейс для присоединения к онлайн-собраниям третьих лиц.</span><span class="sxs-lookup"><span data-stu-id="f8017-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="f8017-105">Если этот параметр включен, вы можете использовать устройство рабочих комнат для присоединения к собраниям, размещенным на Cisco WebEx, и масштаб<sup>1</sup> так же просто, как присоединиться к собраниям, размещенным в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f8017-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="f8017-106">Прежде чем присоединиться к собраниям третьих лиц с устройства с комнатой Teams, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f8017-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="f8017-107">Настройка почтового ящика комнаты на устройстве Teams в помещениях для обработки приглашений на собрания третьих лиц</span><span class="sxs-lookup"><span data-stu-id="f8017-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="f8017-108">Убедитесь, что в вашей организации нет политик, которые не позволят вам подключаться к сторонним службам собраний.</span><span class="sxs-lookup"><span data-stu-id="f8017-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="f8017-109">Настройка устройств, на которых разрешены собрания третьих лиц, с помощью групп комнат</span><span class="sxs-lookup"><span data-stu-id="f8017-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="f8017-110">В следующих разделах описано, как выполнить каждое из этих действий.</span><span class="sxs-lookup"><span data-stu-id="f8017-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="f8017-111">Шаг 1: разрешение обработки приглашения на доступ к календарю для сторонних собраний</span><span class="sxs-lookup"><span data-stu-id="f8017-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="f8017-112">Первое, что нужно сделать, чтобы обеспечить возможность соединения с одним касанием от устройства группы, — это задать правила обработки для почтового ящика комнаты на устройстве Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f8017-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="f8017-113">Для почтового ящика комнаты необходимо разрешить внешние собрания и оставить текст сообщения и тему, чтобы он мог видеть URL-адрес, необходимый для присоединения к собранию стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="f8017-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="f8017-114">Чтобы настроить параметры почтового ящика комнаты с помощью командлета [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f8017-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="f8017-115">Подключитесь к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8017-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="f8017-116">Дополнительные сведения можно найти в разделе [Подключение к Exchange Online PowerShell с обычной проверкой подлинности](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) или [Подключение к Exchange Online PowerShell с помощью многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)в зависимости от метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f8017-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="f8017-117">Если вы не знаете, как получить имя участника-пользователя (UPN) почтового ящика комнаты, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8017-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="f8017-118">Найдите имя почтового ящика комнаты, связанного с устройством "комнаты рабочих групп", и запишите его UPN.</span><span class="sxs-lookup"><span data-stu-id="f8017-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="f8017-119">После того как вы найдете имя участника почтового ящика комнаты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8017-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="f8017-120">Замените на `<UserPrincipalName>` UPN почтового ящика комнаты.</span><span class="sxs-lookup"><span data-stu-id="f8017-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="f8017-121">Дополнительные сведения о [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="f8017-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="f8017-122">Шаг 2: Настройка защиты от угроз для Office 365 и переопределение ссылок</span><span class="sxs-lookup"><span data-stu-id="f8017-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="f8017-123">Чтобы обеспечить возможность соединения с одним касанием, в приглашении на собрание должны быть представлены сведения о связи для присоединения к собранию из другого собрания и могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="f8017-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="f8017-124">Если в вашей организации используется функция [безопасных ссылок на Office 365 Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   или используется стороннее решение, которое проверяет все входящие и исходящие URL-адреса для угроз, может изменить URL-адрес для присоединения к собранию и сделать собрание нераспознаваемым устройством Teams комнаты.</span><span class="sxs-lookup"><span data-stu-id="f8017-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="f8017-125">Чтобы убедиться в том, что это не так, необходимо добавить URL-адреса сторонней службы собраний в список безопасные ссылки ATP "не переписывать", а также список исключений из стороннего URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f8017-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="f8017-126">Чтобы добавить URL-адреса сторонних служб для собраний в список безопасные ссылки ATP "не переписывать", выполните действия, описанные в статье [Настройка настраиваемого списка Do-not-перезапись URL-адресов с помощью безопасных ссылок ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f8017-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="f8017-127">Если вы используете стороннее решение, ознакомьтесь с инструкциями для этого решения, чтобы добавить URL-адреса в список исключений перезаписи URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="f8017-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="f8017-128">Ниже приведено несколько примеров записей, которые может потребоваться добавить в список безопасных ссылок ATP "не переписывать", а также список исключений, перезаписанных сторонним сторонним URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="f8017-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="f8017-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="f8017-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="f8017-130">**Масштаб** `*zoom.us*` , `*zoom.com*``*zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="f8017-130">**Zoom** `*zoom.us*`, `*zoom.com*`, `*zoomgov.com*`</span></span>

<span data-ttu-id="f8017-131">Чтобы получить полный список URL-адресов, которые нужно добавить в список безопасных ссылок ATP "не переписывать", а также список исключений стороннего поставщика, обратитесь к поставщику услуг сторонних разработчиков, с которого вы хотите получать приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="f8017-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="f8017-132">Добавляйте только те URL-адреса, которые вы доверяете, в списке "не переписывать", а также в списке исключений, перезаписанных сторонним сторонним URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="f8017-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="f8017-133">Шаг 3: включение собраний сторонних разработчиков на устройстве</span><span class="sxs-lookup"><span data-stu-id="f8017-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="f8017-134">Последнее действие, которое нужно выполнить, — это разрешить всем устройствам в рабочих группах присоединиться к собраниям третьих лиц.</span><span class="sxs-lookup"><span data-stu-id="f8017-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="f8017-135">Для присоединения к сторонним собраниям требуется имя пользователя и адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8017-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="f8017-136">Если имя пользователя и адрес электронной почты, который вы хотите использовать, отличается от почтового ящика на устройстве, необходимо добавить его на устройство.</span><span class="sxs-lookup"><span data-stu-id="f8017-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="f8017-137">Это можно сделать в разделе Параметры устройства или XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8017-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="f8017-138">Использование параметров устройства</span><span class="sxs-lookup"><span data-stu-id="f8017-138">Use device settings</span></span>

<span data-ttu-id="f8017-139">Чтобы настроить устройство для комнат рабочих групп с помощью сенсорного экрана, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f8017-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="f8017-140">На устройстве Microsoft Teams комнаты выберите **Дополнительно...**</span><span class="sxs-lookup"><span data-stu-id="f8017-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="f8017-141">Выберите **Параметры**, а затем введите имя пользователя и пароль администратора устройства.</span><span class="sxs-lookup"><span data-stu-id="f8017-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="f8017-142">Перейдите на вкладку **собрания**   и выберите **Cisco WebEx**, **масштаб**<sup>1</sup>или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="f8017-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="f8017-143">Если вы хотите присоединиться к собраниям с именем пользователя и адресом электронной почты, связанными с почтовым ящиком комнаты, нажмите кнопку **присоединиться с информацией о комнате**</span><span class="sxs-lookup"><span data-stu-id="f8017-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="f8017-144">Если вы хотите присоединиться к собраниям с альтернативным именем пользователя и адресом электронной почты, выберите команду **присоединиться к настраиваемой информации** и введите имя пользователя и адрес электронной почты, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="f8017-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="f8017-145">Нажмите кнопку **сохранить и выйти**.</span><span class="sxs-lookup"><span data-stu-id="f8017-145">Select **Save and exit**.</span></span> <span data-ttu-id="f8017-146">Ваше устройство будет перезапущено.</span><span class="sxs-lookup"><span data-stu-id="f8017-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="f8017-147">Использование файла конфигурации SkypeSettings.xml</span><span class="sxs-lookup"><span data-stu-id="f8017-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="f8017-148">Следующие параметры могут быть добавлены в файл, `SkypeSettings.xml` находящийся в `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="f8017-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="f8017-149">Дополнительные сведения о `SkypeSettings.xml` файле можно найти в разделе [Управление параметрами консоли Microsoft Teams в удаленном режиме с помощью XML-файла конфигурации](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="f8017-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="f8017-150">Чтобы включить собрания Cisco WebEx, задайте `WebExMeetingsEnabled` для элемента XML значение **true**, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f8017-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="f8017-151">Чтобы включить масштаб<sup>1</sup> собраний, задайте `ZoomMeetingsEnabled` для элемента XML значение **true**, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f8017-151">To enable Zoom<sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="f8017-152">При необходимости вы можете указать имя пользователя и адрес электронной почты, чтобы присоединиться к собраниям третьих лиц, используя следующие элементы XML.</span><span class="sxs-lookup"><span data-stu-id="f8017-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="f8017-153">Если введенные значения не являются допустимыми, по умолчанию будет использоваться имя пользователя почтового ящика комнаты и адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8017-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="f8017-154">Чтобы присоединиться к собранию Cisco WebEx с устройства рабочих комнат, необходимо разместить собрание Cisco с помощью веб-приложения Cisco WebEx версии СДР 40,7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="f8017-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="f8017-155"><sup>одномасштабные</sup> собрания. присоединение в настоящее время доступно только для пользователей Microsoft Teams в рамках программы доступа к технологиям (TAP).</span><span class="sxs-lookup"><span data-stu-id="f8017-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
