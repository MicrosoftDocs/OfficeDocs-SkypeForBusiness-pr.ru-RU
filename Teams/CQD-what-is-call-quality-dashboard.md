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
# <a name="what-is-call-quality-dashboard-cqd"></a>Что такое панель мониторинга качества звонков (CQD)?

Панель мониторинга качества звонков (CQD) — [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) показывает качество звонков и собраний на **уровне Организации**, для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

  
Новейшая версия CQD — [канал данных в ближайшем режиме реального времени (NRT)](CQD-data-and-reports.md), что означает, что в CQD в течение 30 минут до конца звонка будут доступны записи звонков.

Там, где бы CQD включены [данные для конечных пользователей (EUII)](CQD-data-and-reports.md#euii-data), они управляются таким же образом, как и [EUII в Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

CQD предназначен для того, чтобы помочь администраторам Teams, администраторам Skype для бизнеса и сетевым специалистам отслеживать качество звонков и собраний на уровне Организации. Вы будете использовать CQD, чтобы **оптимизировать сеть** для обеспечения качества производительности диска. Если вам нужно найти сведения о звонках и собраниях для **определенного пользователя**, используйте данные CQD в сочетании с [аналитическим вызовом](use-call-analytics-to-troubleshoot-poor-call-quality.md)по каждому пользователю.

Например, с помощью CQD вы можете определить, что неудовлетворительное качество связи пользователя (которое вы пропустили для анализа звонков для пользователей) обусловлено сетевым подключением, которое также влияет на многие другие пользователи. CQD захватывает как индивидуальный звонок, так и общее качество звонков, выполненных с помощью Teams или Skype для бизнеса. С помощью CQD общие шаблоны могут быть заметными, поэтому сетевые инженеры могут оценивать качество связи. CQD предоставляет отчеты о метриках качества связи, которые дают вам общее качество связи, потоки серверных клиентов, потоки клиентов и [соглашения об уровне обслуживания](https://go.microsoft.com/fwlink/p/?linkid=846252)голосовой связи. 
  
![Снимок экрана: панель мониторинга качества звонков.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

В CQD мы рекомендуем вам загрузить сведения о сборке и конечной точке, что позволяет использовать отчеты с расширенными положениями для анализа качества связи и надежности в здании пользователя. Данные могут быть оценены так, чтобы определить, является ли проблема изолированной для одного пользователя или влияет на более крупный сегмент пользователей. Чтобы включить в CQD представления для построения или для конечной точки, администратор должен [добавить сведения о сборке или конечной точке](CQD-upload-tenant-building-data.md) на странице **отправки данных клиента** CQD.

![Снимок экрана: Расширенные отчеты о расположении на панели мониторинга качества звонков.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Не пропустите нашу статью [Управление качеством звонков и собраний](quality-of-experience-review-guide.md) , в которой вы найдете подробные рекомендации для администратора Teams или специалиста службы поддержки, ответственного за управление качеством обслуживания в Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Старая версия CQD (CQD.lync.com)

Текущая версия CQD ( https://CQD.Teams.microsoft.com) заменяет более старую версию CQD ( https://CQD.lync.com) . Вы по-прежнему можете использовать CQD.lync.com (доступное в центре администрирования Skype для бизнеса), но начиная с 1 июля 2020, они используют данные из CQD. Teams.microsoft.com. Мы отправим доступ к CQD.lync.com в скором времени, поэтому вам нужно перейти на CQD. Teams.microsoft.com, если это еще не сделано.

> [!IMPORTANT]
> С 1 июля 2020 г. Вы больше не можете просматривать и изменять данные здания или запроса из старой версии CQD (CQD.lync.com). Если вы еще не передали эти данные из CQD.lync.com и они все еще нужны, зарегистрируйте запрос в службу поддержки.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Анализ данных CQD с помощью Power BI

Новые возможности в январе 2020: [Скачайте шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые шаблоны Power BI, которые можно использовать для анализа и составления отчетов о CQD данных.

Чтение с [помощью Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) для получения дополнительных сведений.



## <a name="related-topics"></a>Связанные статьи

[Улучшение и мониторинг качества связи для Teams](monitor-call-quality-qos.md)

[Настройка панели мониторинга качества звонков (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Отправка клиента и создание данных](CQD-upload-tenant-building-data.md)

[Данные CQD и отчеты](CQD-data-and-reports.md)

[Использование CQD для управления качеством звонков и собраний](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)


[Устранение неполадок Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)