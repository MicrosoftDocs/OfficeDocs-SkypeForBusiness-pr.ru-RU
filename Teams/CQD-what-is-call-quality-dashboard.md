---
title: Что такое панель мониторинга качества звонка?
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
description: Узнайте о панели мониторинга качества звонка и ее использовании для отчетов о качестве собраний и звонка в Microsoft Teams.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094943"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="7d3aa-103">Что такое панель мониторинга качества звонка?</span><span class="sxs-lookup"><span data-stu-id="7d3aa-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="7d3aa-104">Панель мониторинга качества звонков (Microsoft Call Dashboard, CQD) — отображает качество звонков и собраний на уровне организации для Microsoft Teams, Skype для бизнеса Online и [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype для бизнеса Server 2019. </span><span class="sxs-lookup"><span data-stu-id="7d3aa-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="7d3aa-105">Последняя версия CQD содержит веб-канал данных практически в режиме реального времени [(NRT),](CQD-data-and-reports.md)то есть записи вызовов доступны в CQD в течение 30 минут после окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="7d3aa-106">Если CQD содержит личные сведения конечных пользователей [(EUII),](CQD-data-and-reports.md#euii-data)управление им будет тем же способом, что и euII в [Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="7d3aa-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="7d3aa-107">CQD помогает администраторам Teams, администраторам Skype для бизнеса и сетевым инженерам следить за качеством звонков и собраний на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="7d3aa-108">С помощью CQD вы сможете оптимизировать свою сеть для **повышения** качества производительности.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="7d3aa-109">Если вам нужно получить сведения о звонках и собраниях для конкретного **пользователя,** используйте данные CQD вместе с аналитическими данными по звонкам для каждого [пользователя.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="7d3aa-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="7d3aa-110">Например, с помощью CQD можно определить, что низкое качество звонка, которое было наблюдалось при использовании аналитики вызовов "на пользователя", связано с проблемой в сети, которая также наблюдается у многих других пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="7d3aa-111">CQD фиксирует как индивидуальный, так и общее качество звонков, сделанных с помощью Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="7d3aa-112">С помощью CQD общие тенденции могут стать очевидны, поэтому сетевые инженеры могут внести в них обоснованные оценки качества звонка.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="7d3aa-113">CQD предоставляет отчеты о метриках качества звонка, которые дают представление об общем качестве звонка, потоках сервер-клиента, потоках клиент-клиента и SLA о качестве [голосовой почты.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="7d3aa-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Снимок экрана: панель мониторинга качества звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="7d3aa-115">В CQD рекомендуется загружать сведения о здании и конечной точке, что позволяет использовать отчеты Location-Enhanced для анализа качества и надежности звонка в здании пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="7d3aa-116">Данные можно оценить, чтобы определить, изолирована ли проблема для одного пользователя или она влияет на большую часть пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="7d3aa-117">Чтобы включить в CQD представления для здания или [](CQD-upload-tenant-building-data.md) конечной точки, администратор должен добавить сведения о здании или конечной точке на странице отправки данных **клиента** CQD.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Снимок экрана: отчеты о качестве Location-Enhanced звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="7d3aa-119">Не пропустите нашу [](quality-of-experience-review-guide.md) статью "Управление звонками и качеством собраний", которая предлагает подробное руководство для администратора Teams или инженера службы поддержки, отвечающих за управление качеством обслуживания в Teams.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="7d3aa-120">Более старая версия CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="7d3aa-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="7d3aa-121">Текущая версия CQD ( заменяет более старую https://CQD.Teams.microsoft.com) версию CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="7d3aa-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="7d3aa-122">Вы по-прежнему CQD.lync.com приложение (доступно в Центре администрирования Skype для бизнеса), но с 1 июля 2020 г. оно будет использовать данные из CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="7d3aa-123">Мы отключим доступ к CQD.lync.com, поэтому вам следует перейти на CQD. Teams.microsoft.com, если вы еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d3aa-124">С 1 июля 2020 г. вы больше не сможете просматривать или изменять данные здания или запроса из старого CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="7d3aa-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="7d3aa-125">Если вы еще не переносили эти данные из CQD.lync.com и по-прежнему нуждались в них, зайдите в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="7d3aa-126">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="7d3aa-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="7d3aa-127">Новое в январе 2020 г.: скачивание шаблонов [запросов Power BI для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="7d3aa-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="7d3aa-128">Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и отчетов о них.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="7d3aa-129">Дополнительные [сведения об анализе данных CQD](CQD-Power-BI-query-templates.md) с помощью Power BI.</span><span class="sxs-lookup"><span data-stu-id="7d3aa-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="7d3aa-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7d3aa-130">Related topics</span></span>

[<span data-ttu-id="7d3aa-131">Улучшение и отслеживание качества вызова в Teams</span><span class="sxs-lookup"><span data-stu-id="7d3aa-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="7d3aa-132">Настройка панели мониторинга качества звонка (CQD)</span><span class="sxs-lookup"><span data-stu-id="7d3aa-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="7d3aa-133">Отправка данных о клиенте и здании</span><span class="sxs-lookup"><span data-stu-id="7d3aa-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="7d3aa-134">Данные и отчеты CQD</span><span class="sxs-lookup"><span data-stu-id="7d3aa-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="7d3aa-135">Управление звонками и качеством собраний с помощью CQD</span><span class="sxs-lookup"><span data-stu-id="7d3aa-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="7d3aa-136">Измерения и меры, доступные в CQD</span><span class="sxs-lookup"><span data-stu-id="7d3aa-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="7d3aa-137">Классификация потоков в CQD</span><span class="sxs-lookup"><span data-stu-id="7d3aa-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="7d3aa-138">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="7d3aa-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="7d3aa-139">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="7d3aa-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)