---
title: Что такое панель мониторинга качества звонка (CQD)?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Узнайте о панели мониторинга качества звонка (CQD) и о том, как использовать ее для просмотров отчетов о качестве собраний и звонка в Microsoft Teams.
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593837"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="f8e0c-103">Что такое панель мониторинга качества звонка (CQD)?</span><span class="sxs-lookup"><span data-stu-id="f8e0c-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="f8e0c-104">Панель мониторинга качества звонка (Microsoft) — показывает качество звонка и собрания на уровне организации, для Microsoft Teams, Skype для бизнеса Online и [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype для бизнеса Server 2019. </span><span class="sxs-lookup"><span data-stu-id="f8e0c-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="f8e0c-105">Последняя версия CQD содержит веб-канал данных в режиме реального времени [(NRT),](CQD-data-and-reports.md)то есть записи об звонках доступны в CQD в течение 30 минут после окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="f8e0c-106">Если CQD содержит личные сведения конечных пользователей [(EUII),](CQD-data-and-reports.md#euii-data)оно управляется так же, как [и EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)во Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="f8e0c-107">CQD помогает администраторам Teams, администраторам Skype для бизнеса и сетевым инженерам отслеживать качество звонка и собраний на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="f8e0c-108">С помощью CQD вы  сможете оптимизировать сеть для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="f8e0c-109">Если вам нужно посмотреть сведения о звонках и собраниях для определенного **пользователя,** используйте данные CQD в сочетании с аналитическими данными о звонках для [каждого пользователя.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="f8e0c-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="f8e0c-110">Например, с помощью CQD можно определить, что плохое качество звонка (которое наблюдалось при использовании аналитических данных о звонках для каждого пользователя) связано с проблемой в сети, которая также влияет на многих других пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="f8e0c-111">CQD фиксирует как индивидуальный вызов, так и общее качество звонков, Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="f8e0c-112">С помощью CQD общие шаблоны могут стать видимыми, поэтому сетевые инженеры могут в целом оценить качество звонка.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="f8e0c-113">CQD — это отчеты о метриках качества звонка, которые дают представление об общем качестве звонка, потоках сервер-клиент, потоках клиент-клиента и SLA о качестве [голосовой почты.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="f8e0c-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Снимок экрана: панель мониторинга качества звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="f8e0c-115">В CQD мы рекомендуем вам добавить сведения о здании и конечной точке, что позволяет использовать отчеты Location-Enhanced для анализа качества и надежности звонка в пределах здания пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="f8e0c-116">Эти данные можно оценить, чтобы определить, изолирована ли проблема для одного пользователя или она влияет на большую часть пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="f8e0c-117">Чтобы включить представления для здания или конечной точки [](CQD-upload-tenant-building-data.md) в CQD, администратор должен добавить сведения о здании или конечной точке на странице Данные клиента CQD **Upload.**</span><span class="sxs-lookup"><span data-stu-id="f8e0c-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Снимок экрана: панель мониторинга качества Location-Enhanced звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="f8e0c-119">Не пропустите нашу [](quality-of-experience-review-guide.md) статью Управление звонками и качеством собраний, в которой подробно Teams администратора или инженера службы поддержки, отвечающих за управление качеством Teams.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="legacy-version-of-cqd-cqdlynccom"></a><span data-ttu-id="f8e0c-120">Устаревшая версия CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="f8e0c-120">Legacy version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="f8e0c-121">Текущая версия CQD ( заменяет устаревшую https://CQD.Teams.microsoft.com) версию CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="f8e0c-121">The current version of CQD (https://CQD.Teams.microsoft.com) has replaced the legacy version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="f8e0c-122">Вы по-прежнему можете использовать CQD.lync.com (доступно в Центре администрирования Skype для бизнеса), но с 1 июля 2020 г. она использует данные из CQD. Teams.microsoft.com, и вы больше не сможете просматривать и изменять данные здания или запроса из старого CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="f8e0c-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com and you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="f8e0c-123">Если вы еще не переносили эти данные из CQD.lync.com и по-прежнему нуждались в них, зайдите в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-123">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8e0c-124">С 31 июля 2021 г. мы удаляем устаревшую версию CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="f8e0c-124">As of July 31, 2021, we are retiring the legacy version of CQD (CQD.lync.com).</span></span> <span data-ttu-id="f8e0c-125">После этой даты вы будете автоматически перенаправлены в CQD. Teams.microsoft.com при попытке доступа к CQD.lync.com, все неохищенные данные о здании или запросе будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-125">After that date, you will be automatically redirected to CQD.Teams.microsoft.com when attempting to access CQD.lync.com, and any unmigrated building or query data will be lost.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="f8e0c-126">Использование Power BI для анализа данных CQD</span><span class="sxs-lookup"><span data-stu-id="f8e0c-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="f8e0c-127">Новое в январе 2020 г.: [скачивание шаблонов Power BI запросов для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f8e0c-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="f8e0c-128">Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.</span><span class="sxs-lookup"><span data-stu-id="f8e0c-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="f8e0c-129">Дополнительные сведения Power BI статью Использование Power BI для анализа данных [CQD.](CQD-Power-BI-query-templates.md)</span><span class="sxs-lookup"><span data-stu-id="f8e0c-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="f8e0c-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f8e0c-130">Related topics</span></span>

[<span data-ttu-id="f8e0c-131">Улучшение и отслеживание качества звонка для Teams</span><span class="sxs-lookup"><span data-stu-id="f8e0c-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="f8e0c-132">Настройка панели мониторинга качества звонка (CQD)</span><span class="sxs-lookup"><span data-stu-id="f8e0c-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="f8e0c-133">Upload данных о клиенте и здании</span><span class="sxs-lookup"><span data-stu-id="f8e0c-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="f8e0c-134">Данные и отчеты CQD</span><span class="sxs-lookup"><span data-stu-id="f8e0c-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="f8e0c-135">Управление качеством звонка и собрания с помощью CQD</span><span class="sxs-lookup"><span data-stu-id="f8e0c-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="f8e0c-136">Измерения и меры, доступные в CQD</span><span class="sxs-lookup"><span data-stu-id="f8e0c-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="f8e0c-137">Классификация потоков в CQD</span><span class="sxs-lookup"><span data-stu-id="f8e0c-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="f8e0c-138">Использование Power BI для анализа данных CQD</span><span class="sxs-lookup"><span data-stu-id="f8e0c-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="f8e0c-139">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="f8e0c-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
