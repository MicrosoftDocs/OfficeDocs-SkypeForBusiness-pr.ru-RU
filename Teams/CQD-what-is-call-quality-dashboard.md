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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Узнайте о панели мониторинга качества звонка (CQD) и о том, как использовать ее для просмотров отчетов о качестве собраний и звонка в Microsoft Teams.
ms.openlocfilehash: f87f8184b0417d04206d31780392f21dca387d10
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909560"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Что такое панель мониторинга качества звонка (CQD)?

Панель мониторинга качества звонка (Microsoft) — показывает качество звонка и собрания на уровне организации, для Microsoft Teams, Skype для бизнеса Online и [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype для бизнеса Server 2019.  

  
Последняя версия CQD содержит веб-канал данных в режиме реального времени [(NRT),](CQD-data-and-reports.md)то есть записи об звонках доступны в CQD в течение 30 минут после окончания звонка.

Если CQD содержит личные сведения конечных пользователей [(EUII),](CQD-data-and-reports.md#euii-data)управление им будет проходить так же, как [и управление EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)во Microsoft 365.

CQD помогает администраторам Teams, администраторам Skype для бизнеса и сетевым инженерам отслеживать качество звонка и собраний на уровне организации. С помощью CQD вы  сможете оптимизировать сеть для повышения производительности. Если вам нужно посмотреть сведения о звонках и собраниях для определенного **пользователя,** используйте данные CQD в сочетании с аналитическими данными о звонках для [каждого пользователя.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Например, с помощью CQD можно определить, что плохое качество звонка (которое наблюдалось с помощью аналитики вызовов "на пользователя") связано с проблемой в сети, которая также влияет на многих других пользователей. В CQD фиксируется как индивидуальный вызов, так и общее качество звонков, Teams или Skype для бизнеса. С помощью CQD общие шаблоны могут стать явными, поэтому сетевые инженеры могут в целом оценить качество звонка. CQD — это отчеты о показателях качества звонка, которые дают представление об общем качестве звонка, потоках сервер-клиент, потоках клиент-клиента и SLA о качестве [голосовой почты.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Снимок экрана: панель мониторинга качества звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

В CQD мы рекомендуем вам добавить сведения о здании и конечной точке, что позволяет использовать отчеты Location-Enhanced для анализа качества и надежности звонка в пределах здания пользователя. Эти данные можно оценить, чтобы определить, изолирована ли проблема для одного пользователя или она влияет на большую часть пользователей. Чтобы включить представления для здания или конечной точки [](CQD-upload-tenant-building-data.md) в CQD, администратор должен добавить сведения о здании или конечной точке на странице Данные клиента CQD **Upload.**

![Снимок экрана: панель мониторинга качества Location-Enhanced звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Не пропустите нашу [](quality-of-experience-review-guide.md) статью Управление звонками и качеством собраний, в которой подробно Teams администратора или инженера службы поддержки, отвечающих за управление качеством Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Использование Power BI для анализа данных CQD

Новое в январе 2020 [г.: скачивание шаблонов Power BI запросов для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.

Дополнительные сведения Power BI статью Использование Power BI данных [CQD.](CQD-Power-BI-query-templates.md)



## <a name="related-topics"></a>Статьи по теме

[Улучшение и отслеживание качества звонка для Teams](monitor-call-quality-qos.md)

[Настройка панели мониторинга качества звонка (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload данных о клиенте и здании](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление качеством звонка и собрания с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Использование Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md)


[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)
