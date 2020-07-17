---
title: Что такое панель мониторинга качества звонков (CQD)?
ms.author: lolaj
author: LolaJacobsen
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
description: Узнайте о панели мониторинга качества звонков (CQD) и о том, как использовать ее для просмотра отчетов о собрании и связи с качеством звонков в Microsoft Teams.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088247"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="3179e-103">Что такое панель мониторинга качества звонков (CQD)?</span><span class="sxs-lookup"><span data-stu-id="3179e-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="3179e-104">Панель мониторинга качества звонков (CQD) — [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) показывает качество звонков и собраний на **уровне Организации**, для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3179e-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="3179e-105">Новейшая версия CQD — [канал данных в ближайшем режиме реального времени (NRT)](CQD-data-and-reports.md), что означает, что в CQD в течение 30 минут до конца звонка будут доступны записи звонков.</span><span class="sxs-lookup"><span data-stu-id="3179e-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="3179e-106">Там, где бы CQD включены [данные для конечных пользователей (EUII)](CQD-data-and-reports.md#euii-data), они управляются таким же образом, как и [EUII в Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="3179e-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="3179e-107">CQD предназначен для того, чтобы помочь администраторам Teams, администраторам Skype для бизнеса и сетевым специалистам отслеживать качество звонков и собраний на уровне Организации.</span><span class="sxs-lookup"><span data-stu-id="3179e-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="3179e-108">Вы будете использовать CQD, чтобы **оптимизировать сеть** для обеспечения качества производительности диска.</span><span class="sxs-lookup"><span data-stu-id="3179e-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="3179e-109">Если вам нужно найти сведения о звонках и собраниях для **определенного пользователя**, используйте данные CQD в сочетании с [аналитическим вызовом](use-call-analytics-to-troubleshoot-poor-call-quality.md)по каждому пользователю.</span><span class="sxs-lookup"><span data-stu-id="3179e-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="3179e-110">Например, с помощью CQD вы можете определить, что неудовлетворительное качество связи пользователя (которое вы пропустили для анализа звонков для пользователей) обусловлено сетевым подключением, которое также влияет на многие другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="3179e-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="3179e-111">CQD захватывает как индивидуальный звонок, так и общее качество звонков, выполненных с помощью Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3179e-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="3179e-112">С помощью CQD общие шаблоны могут быть заметными, поэтому сетевые инженеры могут оценивать качество связи.</span><span class="sxs-lookup"><span data-stu-id="3179e-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="3179e-113">CQD предоставляет отчеты о метриках качества связи, которые дают вам общее качество связи, потоки серверных клиентов, потоки клиентов и [соглашения об уровне обслуживания](https://go.microsoft.com/fwlink/p/?linkid=846252)голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3179e-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Снимок экрана: панель мониторинга качества звонков.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="3179e-115">В CQD мы рекомендуем вам загрузить сведения о сборке и конечной точке, что позволяет использовать отчеты с расширенными положениями для анализа качества связи и надежности в здании пользователя.</span><span class="sxs-lookup"><span data-stu-id="3179e-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="3179e-116">Данные могут быть оценены так, чтобы определить, является ли проблема изолированной для одного пользователя или влияет на более крупный сегмент пользователей.</span><span class="sxs-lookup"><span data-stu-id="3179e-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="3179e-117">Чтобы включить в CQD представления для построения или для конечной точки, администратор должен [добавить сведения о сборке или конечной точке](CQD-upload-tenant-building-data.md) на странице **отправки данных клиента** CQD.</span><span class="sxs-lookup"><span data-stu-id="3179e-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Снимок экрана: Расширенные отчеты о расположении на панели мониторинга качества звонков.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="3179e-119">Не пропустите нашу статью [Управление качеством звонков и собраний](quality-of-experience-review-guide.md) , в которой вы найдете подробные рекомендации для администратора Teams или специалиста службы поддержки, ответственного за управление качеством обслуживания в Teams.</span><span class="sxs-lookup"><span data-stu-id="3179e-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="3179e-120">Старая версия CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="3179e-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="3179e-121">Текущая версия CQD ( https://CQD.Teams.microsoft.com) заменяет более старую версию CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="3179e-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="3179e-122">Вы по-прежнему можете использовать CQD.lync.com (доступное в центре администрирования Skype для бизнеса), но начиная с 1 июля 2020, они используют данные из CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3179e-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="3179e-123">Мы отправим доступ к CQD.lync.com в скором времени, поэтому вам нужно перейти на CQD. Teams.microsoft.com, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="3179e-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3179e-124">С 1 июля 2020 г. Вы больше не можете просматривать и изменять данные здания или запроса из старой версии CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="3179e-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="3179e-125">Если вы еще не передали эти данные из CQD.lync.com и они все еще нужны, зарегистрируйте запрос в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="3179e-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="3179e-126">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="3179e-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="3179e-127">Новые возможности в январе 2020: [Скачайте шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="3179e-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="3179e-128">Настраиваемые шаблоны Power BI, которые можно использовать для анализа и составления отчетов о CQD данных.</span><span class="sxs-lookup"><span data-stu-id="3179e-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="3179e-129">Чтение с [помощью Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="3179e-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="3179e-130">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3179e-130">Related topics</span></span>

[<span data-ttu-id="3179e-131">Улучшение и мониторинг качества связи для Teams</span><span class="sxs-lookup"><span data-stu-id="3179e-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="3179e-132">Настройка панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="3179e-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="3179e-133">Отправка клиента и создание данных</span><span class="sxs-lookup"><span data-stu-id="3179e-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="3179e-134">Данные CQD и отчеты</span><span class="sxs-lookup"><span data-stu-id="3179e-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="3179e-135">Использование CQD для управления качеством звонков и собраний</span><span class="sxs-lookup"><span data-stu-id="3179e-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="3179e-136">Измерения и меры, доступные в CQD</span><span class="sxs-lookup"><span data-stu-id="3179e-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="3179e-137">Классификация потоков в CQD</span><span class="sxs-lookup"><span data-stu-id="3179e-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="3179e-138">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="3179e-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="3179e-139">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="3179e-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)