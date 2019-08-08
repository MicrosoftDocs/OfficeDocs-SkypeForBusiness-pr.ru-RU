---
title: Настройка параметров трансляции в Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Сведения о том, как управлять параметрами для событий Teams, которые хранятся в Организации.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a1d60ce0e8796d038c6ea8890066c1aee5f0ec6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243706"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="0d949-103">Настройка параметров трансляции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d949-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="0d949-104">Используйте параметры Teams Live Events, чтобы настроить параметры для событий Live Events, которые хранятся в Организации.</span><span class="sxs-lookup"><span data-stu-id="0d949-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="0d949-105">Вы можете настроить URL-адрес службы поддержки и настроить стороннего поставщика услуг для рассылки видео.</span><span class="sxs-lookup"><span data-stu-id="0d949-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="0d949-106">Эти параметры применяются ко всем динамическим событиям, созданным в Организации.</span><span class="sxs-lookup"><span data-stu-id="0d949-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="0d949-107">Эти параметры можно легко настроить в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d949-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0d949-108">На панели навигации слева перейдите к параметрам **собраний** > **Live Events**.</span><span class="sxs-lookup"><span data-stu-id="0d949-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="0d949-109">![Снимок экрана с параметрами команд Live Events] (../media/teams-live-events-settings.png "Снимок экрана с параметрами команд Live Events, которые можно настроить в центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="0d949-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="0d949-110">Настройка URL-адреса службы поддержки событий</span><span class="sxs-lookup"><span data-stu-id="0d949-110">Set up event support URL</span></span>

<span data-ttu-id="0d949-111">Этот URL-адрес отображается участникам интерактивных событий.</span><span class="sxs-lookup"><span data-stu-id="0d949-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="0d949-112">Добавьте URL-адрес поддержки своей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время события Live.</span><span class="sxs-lookup"><span data-stu-id="0d949-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Значок, показывающий логотип Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="0d949-114">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d949-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0d949-115">На панели навигации слева перейдите к параметрам **собраний** > **Live Event**.</span><span class="sxs-lookup"><span data-stu-id="0d949-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="0d949-116">В разделе **URL-адрес службы поддержки**введите URL-адрес своей организации.</span><span class="sxs-lookup"><span data-stu-id="0d949-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="0d949-117">![URL-адрес службы поддержки для событий Live в центре администрирования] (../media/teams-live-events-settings-supporturl.png "Снимок экрана с параметром \"URL-адрес поддержки\" для событий Teams в реальном времени")</span><span class="sxs-lookup"><span data-stu-id="0d949-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="0d949-118">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d949-118">Using Windows PowerShell</span></span>
<span data-ttu-id="0d949-119">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="0d949-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="0d949-120">Дополнительные сведения можно найти в разделе [Set-кстеамсмитингброадкастконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0d949-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="0d949-121">Настройка стороннего поставщика услуг распространения видео</span><span class="sxs-lookup"><span data-stu-id="0d949-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="0d949-122">Если вы приобрели и настроили решение для передачи данных по сети (SDN) или корпоративную сеть доставки содержимого (Екдн) через партнера по доставке Microsoft Video, настройте поставщика для событий Live Events в Teams.</span><span class="sxs-lookup"><span data-stu-id="0d949-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Значок, показывающий логотип Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="0d949-124">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d949-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0d949-125">На панели навигации слева перейдите к параметрам **собраний** > **Live Event**.</span><span class="sxs-lookup"><span data-stu-id="0d949-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="0d949-126">В разделе **сторонние поставщики средств распространения видео**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0d949-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="0d949-127">![Параметры стороннего поставщика услуг распространения видео в центре администрирования] (../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры стороннего поставщика услуг распространения видео для событий Live")</span><span class="sxs-lookup"><span data-stu-id="0d949-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="0d949-128">**Использование стороннего поставщика услуг дистрибуции** Включите этот параметр, чтобы включить стороннего поставщика услуг для рассылки видео.</span><span class="sxs-lookup"><span data-stu-id="0d949-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="0d949-129">**Имя поставщика Sdn** Выберите поставщика, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="0d949-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="0d949-130">**Лицензионный ключ поставщика** Введите идентификатор лицензии, полученный от контакта поставщика.</span><span class="sxs-lookup"><span data-stu-id="0d949-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="0d949-131">**URL-адрес шаблона API Sdn** Введите URL-адрес шаблона API, полученный от контакта поставщика.</span><span class="sxs-lookup"><span data-stu-id="0d949-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="0d949-132">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d949-132">Using Windows PowerShell</span></span>
<span data-ttu-id="0d949-133">Получите идентификатор лицензии или токен API и шаблон API из контакта поставщика, а затем выполните одно из указанных ниже действий в зависимости от используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0d949-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="0d949-134">**Куст**</span><span class="sxs-lookup"><span data-stu-id="0d949-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="0d949-135">**коллективе**</span><span class="sxs-lookup"><span data-stu-id="0d949-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="0d949-136">Дополнительные сведения можно найти в разделе [Set-кстеамсмитингброадкастконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0d949-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="0d949-137">Если вы планируете создавать события Live с помощью внешнего приложения или устройства, вам также потребуется [настроить поставщик екдн с помощью Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="0d949-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="0d949-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0d949-138">Related topics</span></span>
- [<span data-ttu-id="0d949-139">Что такое прямые трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="0d949-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="0d949-140">Планирование прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="0d949-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="0d949-141">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="0d949-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)