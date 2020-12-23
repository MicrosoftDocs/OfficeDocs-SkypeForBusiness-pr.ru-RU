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
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583488"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Что такое панель мониторинга качества звонка?

Панель мониторинга качества звонков (Microsoft Call Dashboard, CQD) — отображает качество звонков и собраний на уровне организации для Microsoft Teams, Skype для бизнеса Online и [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype для бизнеса Server 2019.  

  
Последняя версия CQD содержит веб-канал данных практически в режиме реального времени [(NRT),](CQD-data-and-reports.md)то есть записи вызовов доступны в CQD в течение 30 минут после окончания звонка.

Если CQD содержит личные сведения конечных пользователей [(EUII),](CQD-data-and-reports.md#euii-data)управление им будет тем же способом, что и euII в [Microsoft 365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

CQD помогает администраторам Teams, администраторам Skype для бизнеса и сетевым инженерам отслеживать качество звонков и собраний на уровне организации. С помощью CQD вы  сможете оптимизировать свою сеть для повышения качества производительности. Если вам нужна информация о звонках и собраниях для конкретного **пользователя,** используйте данные CQD вместе с аналитическими данными по звонкам для каждого [пользователя.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Например, с помощью CQD можно определить, что низкое качество звонка, которое было наблюдалось при использовании аналитики вызовов "на пользователя", связано с проблемой в сети, которая также наблюдается у многих других пользователей. CQD фиксирует как индивидуальный, так и общее качество звонков, сделанных с помощью Teams или Skype для бизнеса. С помощью CQD общие тенденции могут стать очевидны, поэтому сетевые инженеры могут внести в них обоснованные оценки качества звонка. CQD предоставляет отчеты о метриках качества звонка, которые дают представление об общем качестве звонка, потоках сервер-клиента, потоках клиент-клиента и SLA о качестве [голосовой почты.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Снимок экрана: панель мониторинга качества звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

В CQD рекомендуется загружать сведения о здании и конечной точке, что позволяет использовать отчеты Location-Enhanced для анализа качества и надежности звонка в здании пользователя. Данные можно оценить, чтобы определить, изолирована ли проблема для одного пользователя или она влияет на более крупные сегменты пользователей. Чтобы включить в CQD представления для здания или [](CQD-upload-tenant-building-data.md) конечной точки, администратор должен добавить сведения о здании или конечной точке на странице отправки данных **клиента** CQD.

![Снимок экрана: отчеты о качестве Location-Enhanced звонка.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Не пропустите нашу [](quality-of-experience-review-guide.md) статью "Управление звонками и качеством собраний", которая предлагает подробное руководство для администратора Teams или инженера службы поддержки, отвечающих за управление качеством обслуживания в Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Более старая версия CQD (CQD.lync.com)

Текущая версия CQD ( заменяет более старую https://CQD.Teams.microsoft.com) версию CQD ( https://CQD.lync.com) . Вы по-прежнему можете использовать CQD.lync.com (доступно в Центре администрирования Skype для бизнеса), но с 1 июля 2020 г. она использует данные из CQD. Teams.microsoft.com. В ближайшее время мы отключим доступ CQD.lync.com, поэтому вам следует перейти на CQD. Teams.microsoft.com, если вы еще не сделали этого.

> [!IMPORTANT]
> С 1 июля 2020 г. вы больше не сможете просматривать или изменять данные здания или запроса из старого CQD (CQD.lync.com). Если вы еще не переносили эти данные из CQD.lync.com и по-прежнему нуждались в них, зайдите в службу поддержки.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Анализ данных CQD с помощью Power BI

Новое в январе 2020 г.: скачивание шаблонов [запросов Power BI для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и отчетов о них.

Дополнительные [сведения об анализе данных CQD](CQD-Power-BI-query-templates.md) с помощью Power BI.



## <a name="related-topics"></a>Статьи по теме

[Улучшение и отслеживание качества вызова в Teams](monitor-call-quality-qos.md)

[Настройка панели мониторинга качества звонка (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Отправка данных о клиенте и здании](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление звонками и качеством собраний с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)


[Устранение неполадок Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)