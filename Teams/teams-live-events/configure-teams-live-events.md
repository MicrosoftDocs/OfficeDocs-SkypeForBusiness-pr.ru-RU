---
title: Настройка параметров трансляции в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Сведения о том, как управлять параметрами для событий Teams, которые хранятся в Организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0e949b2773baa2cc819629133396020dee7d7d7
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203952"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="590cc-103">Настройка параметров трансляции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="590cc-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="590cc-104">Используйте параметры Teams Live Events, чтобы настроить параметры для событий Live Events, которые хранятся в Организации.</span><span class="sxs-lookup"><span data-stu-id="590cc-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="590cc-105">Вы можете настроить URL-адрес службы поддержки и настроить стороннего поставщика услуг для рассылки видео.</span><span class="sxs-lookup"><span data-stu-id="590cc-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="590cc-106">Эти параметры применяются ко всем динамическим событиям, созданным в Организации.</span><span class="sxs-lookup"><span data-stu-id="590cc-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="590cc-107">Эти параметры можно легко настроить в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="590cc-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="590cc-108">На панели навигации слева перейдите к параметрам **собраний**  >  **Live Events**.</span><span class="sxs-lookup"><span data-stu-id="590cc-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="590cc-109">![Снимок экрана с параметрами команд Live Events](../media/teams-live-events-settings.png "Снимок экрана с параметрами команд Live Events, которые можно настроить в центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="590cc-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="590cc-110">Настройка URL-адреса службы поддержки событий</span><span class="sxs-lookup"><span data-stu-id="590cc-110">Set up event support URL</span></span>

<span data-ttu-id="590cc-111">Этот URL-адрес отображается участникам интерактивных событий.</span><span class="sxs-lookup"><span data-stu-id="590cc-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="590cc-112">Добавьте URL-адрес поддержки своей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время события Live.</span><span class="sxs-lookup"><span data-stu-id="590cc-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="590cc-114">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="590cc-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="590cc-115">На панели навигации слева перейдите к параметрам **собраний**  >  **Live Event**.</span><span class="sxs-lookup"><span data-stu-id="590cc-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="590cc-116">В разделе **URL-адрес службы поддержки**введите URL-адрес своей организации.</span><span class="sxs-lookup"><span data-stu-id="590cc-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="590cc-117">![URL-адрес службы поддержки для событий Live в центре администрирования](../media/teams-live-events-settings-supporturl.png "Снимок экрана с параметром "URL-адрес поддержки" для событий Teams в реальном времени")</span><span class="sxs-lookup"><span data-stu-id="590cc-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="590cc-118">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="590cc-118">Using Windows PowerShell</span></span>

<span data-ttu-id="590cc-119">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="590cc-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="590cc-120">Дополнительные сведения можно найти в разделе [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="590cc-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="590cc-121">Настройка стороннего поставщика услуг распространения видео</span><span class="sxs-lookup"><span data-stu-id="590cc-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="590cc-122">Если вы приобрели и настроили решение для передачи данных по сети (SDN) или корпоративную сеть доставки содержимого (eCDN) через партнера по доставке Microsoft Video, настройте поставщика для событий Live Events в Teams.</span><span class="sxs-lookup"><span data-stu-id="590cc-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="590cc-124">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="590cc-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="590cc-125">На панели навигации слева перейдите к параметрам **собраний**  >  **Live Event**.</span><span class="sxs-lookup"><span data-stu-id="590cc-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="590cc-126">В разделе **сторонние поставщики средств распространения видео**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="590cc-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="590cc-127">![Параметры стороннего поставщика услуг распространения видео в центре администрирования](../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры стороннего поставщика услуг распространения видео для событий Live")</span><span class="sxs-lookup"><span data-stu-id="590cc-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="590cc-128">**Использование стороннего поставщика услуг дистрибуции** Включите этот параметр, чтобы включить стороннего поставщика услуг для рассылки видео.</span><span class="sxs-lookup"><span data-stu-id="590cc-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="590cc-129">**Имя поставщика Sdn** Выберите поставщика, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="590cc-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="590cc-130">**Лицензионный ключ поставщика** Введите идентификатор лицензии, полученный от контакта поставщика.</span><span class="sxs-lookup"><span data-stu-id="590cc-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="590cc-131">**URL-адрес шаблона API Sdn** Введите URL-адрес шаблона API, полученный от контакта поставщика.</span><span class="sxs-lookup"><span data-stu-id="590cc-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="590cc-132">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="590cc-132">Using Windows PowerShell</span></span>
<span data-ttu-id="590cc-133">Получите идентификатор лицензии или токен API и шаблон API из контакта поставщика, а затем выполните одно из указанных ниже действий в зависимости от используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="590cc-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="590cc-134">**Куст**</span><span class="sxs-lookup"><span data-stu-id="590cc-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="590cc-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="590cc-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="590cc-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="590cc-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="590cc-137">Дополнительные сведения можно найти в разделе [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="590cc-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="590cc-138">Если вы планируете создавать события Live с помощью внешнего приложения или устройства, вам также потребуется [настроить поставщик eCDN с помощью Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="590cc-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="590cc-139">Поэтапный подход к изменению с помощью Microsoft Stream для [OneDrive для бизнеса и SharePoint для записей собраний](../tmr-meeting-recording-change.md) .</span><span class="sxs-lookup"><span data-stu-id="590cc-139">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="590cc-140">На этапе запуска вы сможете принять участие в этой службе, в ноябре вам придется отказаться от использования потока, и в некоторых случаях на раннем этапе 2021 мы постараемся, чтобы все пользователи могли использовать OneDrive для бизнеса и SharePoint для новых записей о собраниях.</span><span class="sxs-lookup"><span data-stu-id="590cc-140">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="related-topics"></a><span data-ttu-id="590cc-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="590cc-141">Related topics</span></span>
- [<span data-ttu-id="590cc-142">Что такое прямые трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="590cc-142">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="590cc-143">Планирование прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="590cc-143">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="590cc-144">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="590cc-144">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)