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
- m365initiative-meetings-enabler
- enabler-strategic
description: Узнайте, как управлять настройками Teams трансляций, которые проводятся в вашей организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9749484344d969671e8a0195de3386a57388d275
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637881"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="f222f-103">Настройка параметров трансляции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f222f-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="f222f-104">Используйте Teams трансляций, чтобы настроить параметры трансляций, которые проводятся в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f222f-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="f222f-105">Вы можете настроить URL-адрес службы поддержки и стороного поставщика видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="f222f-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="f222f-106">Эти параметры применяются для всех трансляций, созданных в организации.</span><span class="sxs-lookup"><span data-stu-id="f222f-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="f222f-107">Вы можете легко управлять этими настройками в центре Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="f222f-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f222f-108">В левой области навигации перейдите к **настройкам трансляций**  >  **собраний**.</span><span class="sxs-lookup"><span data-stu-id="f222f-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="f222f-109">![Снимок экрана: Teams трансляций](../media/teams-live-events-settings.png "Снимок экрана: Teams трансляций, которые можно настроить в Центре Microsoft Teams администрирования")</span><span class="sxs-lookup"><span data-stu-id="f222f-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="f222f-110">Настройка URL-адреса поддержки событий</span><span class="sxs-lookup"><span data-stu-id="f222f-110">Set up event support URL</span></span>

<span data-ttu-id="f222f-111">Этот URL-адрес отображается для участников трансляции.</span><span class="sxs-lookup"><span data-stu-id="f222f-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="f222f-112">Добавьте URL-адрес службы поддержки вашей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время трансляции.</span><span class="sxs-lookup"><span data-stu-id="f222f-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="f222f-114&quot;>С помощью Центра администрирования Microsoft Teams</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f222f-114&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;f222f-115&quot;>В левой области навигации перейдите в **параметры события**  >  **Meetings Live**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f222f-115&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;f222f-116&quot;>В **области URL-адрес** службы поддержки введите URL-адрес службы поддержки вашей организации.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f222f-116&quot;>Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id=&quot;f222f-117&quot;>![Параметр URL-адреса поддержки для трансляций в Центре администрирования](../media/teams-live-events-settings-supporturl.png &quot;Снимок экрана: URL-адрес службы поддержки для Teams трансляций")</span><span class="sxs-lookup"><span data-stu-id="f222f-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="f222f-118">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f222f-118">Using Windows PowerShell</span></span>

<span data-ttu-id="f222f-119">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="f222f-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="f222f-120">Дополнительные сведения [см. в настройках Set-CsTeamsMeetingBroadcastConfiguration.](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f222f-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="f222f-121">Настройка стороного поставщика видеоконференции</span><span class="sxs-lookup"><span data-stu-id="f222f-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="f222f-122">Если вы приобрели и настроили программное решение для сети (SDN) или корпоративной сети доставки содержимого (eCDN) через партнера Майкрософт по доставке видео, настройте поставщика для трансляций в Teams.</span><span class="sxs-lookup"><span data-stu-id="f222f-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="f222f-124&quot;>С помощью Центра администрирования Microsoft Teams</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f222f-124&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;f222f-125&quot;>В левой области навигации перейдите в **параметры события**  >  **Meetings Live**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f222f-125&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;f222f-126&quot;>В **области Сторонние поставщики видеоконференции** выполните следующие этапы:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f222f-126&quot;>Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id=&quot;f222f-127&quot;>![Параметры сторонного поставщика видеоконференции в Центре администрирования](../media/teams-live-events-settings-distribution-provider.png &quot;Снимок экрана: параметры сторонного поставщика видеоконференции для трансляций")</span><span class="sxs-lookup"><span data-stu-id="f222f-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="f222f-128">**Использование стороного поставщика рассылки** Включим эту возможность, чтобы включить стороного поставщика видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="f222f-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="f222f-129">**Имя поставщика SDN** Выберите поставщика, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="f222f-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="f222f-130">**Ключ лицензии поставщика** Введите номер лицензии, который вы получили от своего поставщика.</span><span class="sxs-lookup"><span data-stu-id="f222f-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="f222f-131">**URL-адрес шаблона API SDN** Введите URL-адрес шаблона API, который вы получили от своего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="f222f-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="f222f-132">Использование Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f222f-132">Using Windows PowerShell</span></span>
<span data-ttu-id="f222f-133">Получите от своего поставщика удостоверение лицензии или маркер API и шаблон API, а затем запустите один из следующих решений в зависимости от используемого поставщика:</span><span class="sxs-lookup"><span data-stu-id="f222f-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="f222f-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="f222f-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="f222f-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="f222f-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="f222f-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="f222f-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
<span data-ttu-id="f222f-137">**Ramp**</span><span class="sxs-lookup"><span data-stu-id="f222f-137">**Ramp**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

<span data-ttu-id="f222f-138">Дополнительные сведения [см. в настройках Set-CsTeamsMeetingBroadcastConfiguration.](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f222f-138">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="f222f-139">Если вы планируете создавать трансляции с помощью внешнего приложения или устройства, вам также потребуется настроить поставщика [eCDN в Microsoft Stream.](/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="f222f-139">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="f222f-p104">Переход с использования Microsoft Stream на [OneDrive для бизнеса и SharePoint для записей собраний](../tmr-meeting-recording-change.md) будет поэтапным процессом. При запуске вы сможете согласиться на использование этого интерфейса. В ноябре потребуется отказаться от использования, если вы хотите продолжить использование Stream. В начале 2021 г. мы сделаем использование OneDrive для бизнеса и SharePoint для новых записей собраний обязательным для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f222f-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

>[!Note]
> <span data-ttu-id="f222f-142">Выбранное решение eCDN регулируется условиями обслуживания и политикой конфиденциальности сторон, которые регулируют использование решения поставщика eCDN.</span><span class="sxs-lookup"><span data-stu-id="f222f-142">Your chosen eCDN solution is subject to the selected 3rd party provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="f222f-143">Использование решения поставщика eCDN не будет под тем же соглашением об условиях корпоративного лицензирования Майкрософт или Условиями онлайн-сервисов.</span><span class="sxs-lookup"><span data-stu-id="f222f-143">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="f222f-144">Если вы не согласны с условиями сторонних поставщиков, не в включаете решение eCDN в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f222f-144">If you don't agree to the 3rd party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.</span></span>

### <a name="related-topics"></a><span data-ttu-id="f222f-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f222f-145">Related topics</span></span>
- [<span data-ttu-id="f222f-146">Что такое прямые трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="f222f-146">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="f222f-147">Планирование прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="f222f-147">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="f222f-148">Настройка прямых трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="f222f-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
