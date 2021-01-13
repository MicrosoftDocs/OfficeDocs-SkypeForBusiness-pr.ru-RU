---
title: Настройка параметров трансляции в Microsoft Teams
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
- enabler-strategic
description: Узнайте, как управлять настройками для трансляций Teams, которые проводятся в вашей организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831199"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="91b6e-103">Настройка параметров трансляции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91b6e-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="91b6e-104">Используйте параметры трансляций Teams для настройки параметров трансляций, которые проводятся в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="91b6e-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="91b6e-105">Вы можете настроить URL-адрес службы поддержки и сторонних поставщиков видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="91b6e-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="91b6e-106">Эти параметры применяются для всех трансляций, созданных в организации.</span><span class="sxs-lookup"><span data-stu-id="91b6e-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="91b6e-107">Вы можете легко управлять этими настройками в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="91b6e-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="91b6e-108">В области навигации слева перейдите к **настройкам трансляций**  >  **собраний.**</span><span class="sxs-lookup"><span data-stu-id="91b6e-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="91b6e-109">![Снимок экрана: параметры трансляций Teams](../media/teams-live-events-settings.png "Снимок экрана: параметры трансляций Teams, которые можно настроить в Центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="91b6e-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="91b6e-110">НАСТРОЙКА URL-адреса поддержки событий</span><span class="sxs-lookup"><span data-stu-id="91b6e-110">Set up event support URL</span></span>

<span data-ttu-id="91b6e-111">Этот URL-адрес отображается для участников трансляции.</span><span class="sxs-lookup"><span data-stu-id="91b6e-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="91b6e-112">Добавьте URL-адрес службы поддержки для вашей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время трансляции.</span><span class="sxs-lookup"><span data-stu-id="91b6e-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="91b6e-114">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91b6e-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="91b6e-115">В области навигации слева перейдите к **настройкам**  >  **трансляции собраний.**</span><span class="sxs-lookup"><span data-stu-id="91b6e-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="91b6e-116">Введите **URL-адрес** службы поддержки своей организации.</span><span class="sxs-lookup"><span data-stu-id="91b6e-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="91b6e-117">![Параметр URL-адреса поддержки трансляций в Центре администрирования](../media/teams-live-events-settings-supporturl.png "Снимок экрана: параметр URL-адреса поддержки для трансляций Teams")</span><span class="sxs-lookup"><span data-stu-id="91b6e-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="91b6e-118">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91b6e-118">Using Windows PowerShell</span></span>

<span data-ttu-id="91b6e-119">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="91b6e-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="91b6e-120">Дополнительные сведения [см. в set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="91b6e-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="91b6e-121">Настройка стороного поставщика видеоконференции</span><span class="sxs-lookup"><span data-stu-id="91b6e-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="91b6e-122">Если вы приобрели и настроили программное решение для сети (SDN) или корпоративной сети доставки содержимого (eCDN) через партнера Майкрософт по доставке видео, настройте его для трансляций в Teams.</span><span class="sxs-lookup"><span data-stu-id="91b6e-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="91b6e-124">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91b6e-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="91b6e-125">В области навигации слева перейдите к **настройкам**  >  **трансляции собраний.**</span><span class="sxs-lookup"><span data-stu-id="91b6e-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="91b6e-126">В **области сторонних поставщиков видеоконференции** выполните следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="91b6e-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="91b6e-127">![Параметры сторонного поставщика видеоконференции в Центре администрирования](../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры сторонного поставщика видеоконференции для трансляций")</span><span class="sxs-lookup"><span data-stu-id="91b6e-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="91b6e-128">**Использование стороного поставщика рассылки** Включим эту возможность, чтобы включить стороного поставщика видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="91b6e-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="91b6e-129">**Имя поставщика SDN** Выберите поставщика.</span><span class="sxs-lookup"><span data-stu-id="91b6e-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="91b6e-130">**Ключ лицензии поставщика** Введите номер лицензии, который вы получили у своего контакта поставщика.</span><span class="sxs-lookup"><span data-stu-id="91b6e-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="91b6e-131">**URL-адрес шаблона API SDN** Введите URL-адрес шаблона API, который вы получили у своего поставщика.</span><span class="sxs-lookup"><span data-stu-id="91b6e-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="91b6e-132">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91b6e-132">Using Windows PowerShell</span></span>
<span data-ttu-id="91b6e-133">Получите у контакта поставщика ИД лицензии или маркер API и шаблон API, а затем запустите один из следующих решений в зависимости от используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="91b6e-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="91b6e-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="91b6e-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="91b6e-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="91b6e-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="91b6e-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="91b6e-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="91b6e-137">Дополнительные сведения [см. в set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="91b6e-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="91b6e-138">Если вы планируете создавать трансляции с помощью внешнего приложения или устройства, необходимо также настроить поставщика [услуг eCDN в Microsoft Stream.](https://docs.microsoft.com/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="91b6e-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="91b6e-p104">Переход с использования Microsoft Stream на [OneDrive для бизнеса и SharePoint для записей собраний](../tmr-meeting-recording-change.md) будет поэтапным процессом. При запуске вы сможете согласиться на использование этого интерфейса. В ноябре потребуется отказаться от использования, если вы хотите продолжить использование Stream. В начале 2021 г. мы сделаем использование OneDrive для бизнеса и SharePoint для новых записей собраний обязательным для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="91b6e-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="related-topics"></a><span data-ttu-id="91b6e-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="91b6e-141">Related topics</span></span>
- [<span data-ttu-id="91b6e-142">Что такое прямые трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="91b6e-142">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="91b6e-143">Планирование прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="91b6e-143">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="91b6e-144">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="91b6e-144">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
