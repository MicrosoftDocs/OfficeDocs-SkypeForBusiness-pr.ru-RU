---
title: Что такое панель мониторинга качества звонков (CQD)?
author: CarolynRowe
ms.author: crowe
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
description: Узнайте о панели мониторинга качества звонков (CQD) и о том, как использовать ее для просмотра отчетов о качестве собраний и звонков в Microsoft Teams.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790074"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Что такое панель мониторинга качества звонков (CQD)?

Панель мониторинга качества звонков (CQD) (Майкрософт) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) — отображает качество звонков и собраний на уровне **организации для Microsoft** Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

  
Последняя версия CQD содержит веб-канал данных практически в реальном времени [(NRT](CQD-data-and-reports.md)), что означает, что записи вызовов доступны в CQD в течение 30 минут после завершения вызова.

Если CQD включает данные, идентифицируемые конечным пользователем [(EUII](CQD-data-and-reports.md#euii-data)), управление осуществляется так же, как [EUII в Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

CQD предназначен для того, чтобы помочь администраторам Teams, Skype для бизнеса администраторам и сетевым инженерам отслеживать качество звонков и собраний на уровне организации. Вы будете использовать CQD, чтобы оптимизировать **сеть для** повышения производительности. Если вам нужно просмотреть сведения о звонках и собраниях для определенного **пользователя, используйте** данные CQD в сочетании с аналитикой звонков для [каждого пользователя](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Например, с помощью CQD можно определить, что низкое качество звонков пользователя (которое вы наблюдаете с помощью аналитики звонков для отдельных пользователей) связано с проблемой сети, которая также влияет на многих других пользователей. CQD фиксирует как индивидуальный интерфейс звонков, так и общее качество звонков, выполненных с помощью Teams или Skype для бизнеса. При CQD общие шаблоны могут стать очевидными, поэтому сетевые инженеры могут взвешенную оценку качества звонков. CQD предоставляет отчеты о метриках качества звонков, которые позволяют получить представление об общем качестве звонков, потоках сервер-клиент, потоках клиента и соглашении об уровне обслуживания качества [голосовой связи](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Снимок экрана: панель мониторинга качества звонков.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

В CQD мы рекомендуем отправлять сведения о сборке и конечной точке, что позволяет использовать отчеты Location-Enhanced для анализа качества и надежности звонков в здании пользователя. Данные можно оценить, чтобы определить, является ли проблема изолированной для одного пользователя или затрагивает больший сегмент пользователей. Чтобы включить создание представлений или представлений конечной точки в CQD, администратор должен [](CQD-upload-tenant-building-data.md) отправить сведения о сборке или конечной точке на странице отправки данных клиента CQD **.**

![Снимок экрана: панель мониторинга качества звонков Location-Enhanced отчетов.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Не пропустите нашу статью [](quality-of-experience-review-guide.md) "Управление качеством звонков и собраний", которая содержит подробные рекомендации для администратора Teams или инженера службы поддержки, ответственного за управление качеством обслуживания в Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Анализ данных CQD с помощью Power BI

Новые возможности в январе 2020 г [.: скачивание шаблонов запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и создания отчетов о них.

Дополнительные сведения см. в описании использования [Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) .



## <a name="related-topics"></a>См. также

[Улучшение и мониторинг качества звонков для Teams](monitor-call-quality-qos.md)

[Настройка панели мониторинга качества звонков (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Отправка данных о клиенте и сборке](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление качеством звонков и собраний с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)


[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)
