---
title: Настройка параметров live события в группами Майкрософт
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Узнайте, как управлять параметрами для групп live события, которые хранятся в вашей организации.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8e12b6b85b61bb8c6312054be07dc37365c62c0
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532251"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="11de6-103">Настройка параметров live события в группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="11de6-103">Configure live event settings in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="11de6-104">Используйте параметры групп событий в реальном времени для настройки параметров для live события, которые хранятся в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11de6-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="11de6-105">Можно настроить URL-адрес поддержки и настроить распределение видео стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="11de6-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="11de6-106">Эти параметры применяются ко всем событиям live, которые созданы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11de6-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="11de6-107">Можно легко управлять эти параметры в группами Майкрософт & Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="11de6-107">You can easily manage these settings in the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="11de6-108">В левой области переходов, перейдите к **собраниям** > **Параметры событий в реальном времени**.</span><span class="sxs-lookup"><span data-stu-id="11de6-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="11de6-109">![Live — событие settings.png] (../media/teams-live-events-settings.png "Снимок экрана команды live настройки событий, которые можно настроить в группами Майкрософт & Скайп по центру администрирования бизнеса")</span><span class="sxs-lookup"><span data-stu-id="11de6-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams & Skype for Business admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="11de6-110">Настройка URL-адрес поддержки событий</span><span class="sxs-lookup"><span data-stu-id="11de6-110">Set up event support URL</span></span>

<span data-ttu-id="11de6-111">Этот URL-адрес отображается в live участников события.</span><span class="sxs-lookup"><span data-stu-id="11de6-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="11de6-112">Добавление поддержки URL-адрес для своей организации для предоставления возможности обратиться в службу поддержки во время события live участников.</span><span class="sxs-lookup"><span data-stu-id="11de6-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![команды логотип 30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="11de6-114">Использование групп Майкрософт & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="11de6-114">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="11de6-115">В левой области переходов, перейдите к **собраниям** > **Параметры Live событий**.</span><span class="sxs-lookup"><span data-stu-id="11de6-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="11de6-116">В группе **Поддержки URL-адрес**введите URL-адрес поддержки вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11de6-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="11de6-117">![Параметр URL-адреса поддержки для live события в группами Майкрософт & Скайп по центру администрирования бизнеса] (../media/teams-live-events-settings-supporturl.png "Снимок экрана поддерживает URL-адрес, задание для групп событий в реальном времени")</span><span class="sxs-lookup"><span data-stu-id="11de6-117">![Support URL setting for live events in the Microsoft Teams & Skype for Business admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="11de6-118">С помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11de6-118">Using Windows PowerShell</span></span>
<span data-ttu-id="11de6-119">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="11de6-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="11de6-120">Для получения дополнительных сведений см [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="11de6-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="11de6-121">Настройка распределение видео стороннего поставщика</span><span class="sxs-lookup"><span data-stu-id="11de6-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="11de6-122">Если приобретается и настройка решения сети (SDN) определенного программного обеспечения или корпоративной сети (eCDN) решение через партнером Майкрософт и видео доставки настройте поставщика для событий в реальном времени в группах.</span><span class="sxs-lookup"><span data-stu-id="11de6-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![команды логотип 30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="11de6-124">Использование групп Майкрософт & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="11de6-124">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="11de6-125">В левой области переходов, перейдите к **собраниям** > **Параметры Live событий**.</span><span class="sxs-lookup"><span data-stu-id="11de6-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="11de6-126">В разделе **сторонние поставщики распределение видео**установите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="11de6-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="11de6-127">![Параметры поставщика распределение видео сторонних производителей в группами Майкрософт & Скайп по центру администрирования Business] (../media/teams-live-events-settings-distribution-provider.png "Снимок экрана параметров поставщика распределение видео сторонних производителей для события")</span><span class="sxs-lookup"><span data-stu-id="11de6-127">![Third-party video distribution provider settings in the Microsoft Teams & Skype for Business admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="11de6-128">**Использование рассылки стороннего поставщика** Отключите этот вход в систему включить распределение видео стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="11de6-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="11de6-129">**Имя поставщика SDN** Выберите поставщика, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="11de6-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="11de6-130">**Ключ многократной установки поставщика** Введите код лицензии, полученный из контактов поставщика.</span><span class="sxs-lookup"><span data-stu-id="11de6-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="11de6-131">**URL-адрес шаблона SDN API** Введите URL-адрес шаблона API, полученный от поставщика контакт.</span><span class="sxs-lookup"><span data-stu-id="11de6-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="11de6-132">С помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11de6-132">Using Windows PowerShell</span></span>
<span data-ttu-id="11de6-133">Получение маркера лицензии идентификатор или интерфейса API и шаблона API из контактов поставщика и затем выполните одно из следующих действий в зависимости от поставщика, который вы используете:</span><span class="sxs-lookup"><span data-stu-id="11de6-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="11de6-134">**Куст**</span><span class="sxs-lookup"><span data-stu-id="11de6-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="11de6-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="11de6-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="11de6-136">Для получения дополнительных сведений см [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="11de6-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="11de6-137">Если планируется создание live событий, использующих внешний кодировщики, необходимо также [настроить поставщика eCDN с Microsoft потока](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="11de6-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="11de6-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="11de6-138">Related topics</span></span>
- [<span data-ttu-id="11de6-139">Что такое группы live событий?</span><span class="sxs-lookup"><span data-stu-id="11de6-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="11de6-140">Планирование групп событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="11de6-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="11de6-141">Настройка для групп событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="11de6-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)