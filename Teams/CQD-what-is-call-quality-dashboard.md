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
ms.openlocfilehash: 097a12c0e2a7104abe9a6214a24c958b5c3f6b6e2430f78b05aeef6e0f79736f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344488"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Что такое панель мониторинга качества звонка (CQD)?

Панель мониторинга качества звонка (Microsoft) — показывает качество звонка и собрания на уровне организации, для Microsoft Teams, Skype для бизнеса Online и [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype для бизнеса Server 2019.  

  
Последняя версия CQD содержит веб-канал данных в режиме реального времени [(NRT),](CQD-data-and-reports.md)то есть записи об звонках доступны в CQD в течение 30 минут после окончания звонка.

Если CQD содержит личные сведения конечных пользователей [(EUII),](CQD-data-and-reports.md#euii-data)оно управляется так же, как [и EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)во Microsoft 365.

CQD помогает администраторам Teams, администраторам Skype для бизнеса и сетевым инженерам следить за качеством звонка и собрания на уровне организации. С помощью CQD вы  сможете оптимизировать сеть для повышения производительности. Если вам нужно посмотреть сведения о звонках и собраниях для определенного **пользователя,** используйте данные CQD в сочетании с аналитическими данными о звонках для [каждого пользователя.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Например, с помощью CQD можно определить, что плохое качество звонка (которое наблюдалось с помощью аналитики вызовов "на пользователя") связано с проблемой в сети, которая также влияет на многих других пользователей. В CQD фиксируется как индивидуальный вызов, так и общее качество звонков, Teams или Skype для бизнеса. С помощью CQD общие шаблоны могут стать видимыми, поэтому сетевые инженеры могут в целом оценить качество звонка. CQD — это отчеты о метриках качества звонка, которые дают представление об общем качестве звонка, потоках сервер-клиент, потоках клиент-клиента и SLA о качестве [голосовой почты.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Снимок экрана: панель мониторинга качества звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

В CQD мы рекомендуем вам добавить сведения о здании и конечной точке, что позволяет использовать отчеты Location-Enhanced для анализа качества и надежности звонка в пределах здания пользователя. Эти данные можно оценить, чтобы определить, изолирована ли проблема для одного пользователя или она влияет на большую часть пользователей. Чтобы включить представления для здания или конечной точки [](CQD-upload-tenant-building-data.md) в CQD, администратор должен добавить сведения о здании или конечной точке на странице Данные клиента CQD **Upload.**

![Снимок экрана: панель мониторинга качества Location-Enhanced звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Не пропустите нашу [](quality-of-experience-review-guide.md) статью Управление звонками и качеством собраний, в которой подробно Teams администратора или инженера службы поддержки, отвечающих за управление качеством Teams.

## <a name="legacy-version-of-cqd-cqdlynccom"></a>Устаревшая версия CQD (CQD.lync.com)

Текущая версия CQD ( заменяет устаревшую https://CQD.Teams.microsoft.com) версию CQD ( https://CQD.lync.com) . Вы по-прежнему можете использовать CQD.lync.com (доступно в Центре администрирования Skype для бизнеса), но с 1 июля 2020 г. она использует данные из CQD. Teams.microsoft.com, и вы больше не сможете просматривать и изменять данные здания или запроса из старого CQD (CQD.lync.com). Если вы еще не переносили эти данные из CQD.lync.com и по-прежнему нуждались в них, зайдите в службу поддержки.

> [!IMPORTANT]
> С 31 июля 2021 г. мы удаляем устаревшую версию CQD (CQD.lync.com). После этой даты вы будете автоматически перенаправлены в CQD. Teams.microsoft.com при попытке доступа к CQD.lync.com, все неохищенные данные о здании или запросе будут потеряны.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Использование Power BI для анализа данных CQD

Новое в январе 2020 г.: [скачивание шаблонов Power BI запросов для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.

Дополнительные сведения Power BI статью Использование Power BI для анализа данных [CQD.](CQD-Power-BI-query-templates.md)



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
