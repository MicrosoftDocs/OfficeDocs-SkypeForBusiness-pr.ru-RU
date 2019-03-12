---
title: Настройка параметров трансляции в Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Узнайте, как управлять параметрами для групп live события, которые хранятся в вашей организации.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56a7834f1547c682c690f8c42082af0a314efec9
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542841"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="53e88-103">Настройка параметров трансляции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53e88-103">Configure live event settings in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="53e88-104">Используйте параметры групп событий в реальном времени для настройки параметров для live события, которые хранятся в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="53e88-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="53e88-105">Можно настроить URL-адрес поддержки и настроить распределение видео стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="53e88-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="53e88-106">Эти параметры применяются ко всем событиям live, которые созданы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="53e88-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="53e88-107">Можно легко управлять эти параметры в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="53e88-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="53e88-108">В левой области переходов, перейдите к **собраниям** > **Параметры событий в реальном времени**.</span><span class="sxs-lookup"><span data-stu-id="53e88-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="53e88-109">![Live — событие settings.png] (../media/teams-live-events-settings.png "Снимок экрана команды live настройки событий, которые можно настроить в центре администрирования группами Майкрософт")</span><span class="sxs-lookup"><span data-stu-id="53e88-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="53e88-110">Настройка URL-адрес поддержки событий</span><span class="sxs-lookup"><span data-stu-id="53e88-110">Set up event support URL</span></span>

<span data-ttu-id="53e88-111">Этот URL-адрес отображается в live участников события.</span><span class="sxs-lookup"><span data-stu-id="53e88-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="53e88-112">Добавление поддержки URL-адрес для своей организации для предоставления возможности обратиться в службу поддержки во время события live участников.</span><span class="sxs-lookup"><span data-stu-id="53e88-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![команды логотип 30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="53e88-114">С помощью центра администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="53e88-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="53e88-115">В левой области переходов, перейдите к **собраниям** > **Параметры Live событий**.</span><span class="sxs-lookup"><span data-stu-id="53e88-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="53e88-116">В группе **Поддержки URL-адрес**введите URL-адрес поддержки вашей организации.</span><span class="sxs-lookup"><span data-stu-id="53e88-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="53e88-117">![Параметр URL-адреса поддержки для события в центре администрирования группами Майкрософт] (../media/teams-live-events-settings-supporturl.png "Снимок экрана поддерживает URL-адрес, задание для групп событий в реальном времени")</span><span class="sxs-lookup"><span data-stu-id="53e88-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="53e88-118">С помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53e88-118">Using Windows PowerShell</span></span>
<span data-ttu-id="53e88-119">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="53e88-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="53e88-120">Для получения дополнительных сведений см [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53e88-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="53e88-121">Настройка распределение видео стороннего поставщика</span><span class="sxs-lookup"><span data-stu-id="53e88-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="53e88-122">Если приобретается и настройка решения сети (SDN) определенного программного обеспечения или корпоративной сети (eCDN) решение через партнером Майкрософт и видео доставки настройте поставщика для событий в реальном времени в группах.</span><span class="sxs-lookup"><span data-stu-id="53e88-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![команды логотип 30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="53e88-124">С помощью центра администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="53e88-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="53e88-125">В левой области переходов, перейдите к **собраниям** > **Параметры Live событий**.</span><span class="sxs-lookup"><span data-stu-id="53e88-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="53e88-126">В разделе **сторонние поставщики распределение видео**установите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="53e88-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="53e88-127">![Параметры поставщика сторонних производителей распределение видео в центре администрирования группами Майкрософт] (../media/teams-live-events-settings-distribution-provider.png "Снимок экрана параметров поставщика распределение видео сторонних производителей для события")</span><span class="sxs-lookup"><span data-stu-id="53e88-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="53e88-128">**Использование рассылки стороннего поставщика** Отключите этот вход в систему включить распределение видео стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="53e88-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="53e88-129">**Имя поставщика SDN** Выберите поставщика, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="53e88-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="53e88-130">**Ключ многократной установки поставщика** Введите код лицензии, полученный из контактов поставщика.</span><span class="sxs-lookup"><span data-stu-id="53e88-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="53e88-131">**URL-адрес шаблона SDN API** Введите URL-адрес шаблона API, полученный от поставщика контакт.</span><span class="sxs-lookup"><span data-stu-id="53e88-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="53e88-132">С помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53e88-132">Using Windows PowerShell</span></span>
<span data-ttu-id="53e88-133">Получение маркера лицензии идентификатор или интерфейса API и шаблона API из контактов поставщика и затем выполните одно из следующих действий в зависимости от поставщика, который вы используете:</span><span class="sxs-lookup"><span data-stu-id="53e88-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="53e88-134">**Куст**</span><span class="sxs-lookup"><span data-stu-id="53e88-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="53e88-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="53e88-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="53e88-136">Для получения дополнительных сведений см [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53e88-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="53e88-137">Если планируется создание live событий, использующих внешний кодировщики, необходимо также [настроить поставщика eCDN с Microsoft потока](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="53e88-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="53e88-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="53e88-138">Related topics</span></span>
- [<span data-ttu-id="53e88-139">Что такое прямые трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="53e88-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="53e88-140">Планирование прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="53e88-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="53e88-141">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="53e88-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)