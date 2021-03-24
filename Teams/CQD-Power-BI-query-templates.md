---
title: Анализ данных CQD для Microsoft Teams с помощью Power BI
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Используйте Power BI для анализа данных CQD для Microsoft Teams.
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096525"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Анализ данных CQD для Microsoft Teams с помощью Power BI

Новое в январе 2020 г.: скачивание шаблонов [запросов Power BI для CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и отчетов о них.

Если вы хотите запрашивать данные и сообщать о них с помощью Power BI, скачайте наши шаблоны CQD Power BI для отчетов о качестве звонка в Teams. Когда вы откроете шаблоны в Power BI, вам будет предложено войти с учетными данными администратора CQD. Вы можете настроить эти шаблоны запросов и распространить их всем в организации с лицензиями на Power BI и разрешениями администратора CQD.

Прежде чем использовать эти PBIT-файлы, необходимо установить Power BI Connector для [Microsoft CQD,](CQD-Power-BI-connector.md) используя *файл MicrosoftCallQuality.pqx,* включенный в скачаемый [файл.](https://www.microsoft.com/download/details.aspx?id=102291) 

Убедитесь, что у вас есть права на доступ к отчетам Power BI с правильной ролью "Доступ к [CQD".](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 

|  |  |
|---------|---------|
|<strong>(Новое!).</strong> CQD Teams автосекретарь & история отчетов об очереди вызовов.pbit     |  Этот шаблон содержит три отчета:</p><li>автосекретарь показаны аналитические данные по звонкам, которые в него взламываемы автоответам.</li><li>Очереди звонков— аналитические данные о звонках, которые будут в очередях звонков.</li><li>Временная шкала агента— отображение временной шкалы, в которой агенты активны в звонках очереди звонков.</li><br>Дополнительные данные можно найти в [автосекретарь & учитее отчета об очереди вызовов.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |Интегрируя данные о здании и данных EUII, этот отчет предназначен для того, чтобы вы могли получить данные от одного пользователя в качестве основной причины низкого качества звонка (например, пользователь находится в здании, в которое возникли проблемы с сетью).         |
|CQD Location Enhanced Report.pbit     | Переопоминание отчетов о расположении CQD SPD. Содержит 9 отчетов, включающих сведения о качестве звонка, построении Wi-Fi, надежности и ставке звонка (RMC), а также дополнительных возможности drill-thrus по зданиям или по пользователям.  Обязательно загрузите данные о здании, чтобы расширить отчеты.        |
|CQD Mobile Device Report.pbit     | Предоставляет сведения, предназначенные специально для пользователей мобильных устройств, в том числе о качестве и надежности звонка, а также о том, как оценить мой звонок. Просмотр отчетов о мобильной сети, сети Wi-Fi и операционных системах мобильных устройств (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Предоставляет сведения о звонках по ННР, которые проходят прямую маршрутику. Подробнее об этом можно узнать в [отчете CQD "Прямая маршрутка по ННР".](CQD-PSTN-report.md)         |
|CQD Summary Report.pbit     |Улучшенная визуализация, улучшенная презентация, повышенная плотность информации и даты ветвя. Эти отчеты упрощают определение выбросов. Изумить качество звонка по расположению с помощью удобной интерактивной карты. 9 новых отчетов:</p>- Общее качество<br>- Надежность в целом<br>- RMC (rate My Call) Overall<br>- Качество конференции<br>- Качество P2P<br>- Надежность конференции<br>- Надежность P2P<br>- Конференция RMC<br>- P2P RMC         |
|<strong>(Новое!).</strong> CQD Teams Utilization Report.pbit     | Показывает, как пользователи в вашей организации используют Teams и в какой степени. Обязательно загрузите данные о здании, чтобы расширить отчеты. Чтобы узнать больше, ознакомьтесь с использованием отчета [CQD Power BI для просмотра](CQD-teams-utilization-report.md)использования Microsoft Teams.        |
|CQD User Feedback (Rate My Call) Report.pbit     | Показано, как оценить данные моих звонков, чтобы помочь вам со звонить в вашу организацию. Перекрестная ссылка с глаголами для определения возможностей обучения конечных пользователей.        |

> [!TIP]
> После того как вы настроите отчеты Power BI для данных CQD, добавьте их в канал в качестве вкладки. Выбрав **+** канал, выберите **Power BI** и найдите отчет. Чтобы узнать больше, ознакомьтесь с [отчетом Embed с помощью вкладки Power BI для Teams.](/power-bi/service-embed-report-microsoft-teams) Помните, что доступ к этим отчетам могут получить только люди с лицензией на Power BI и учетными данными администратора CQD.


## <a name="related-topics"></a>Статьи по теме

[Измерения и меры на панели мониторинга качества звонков](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков на панели мониторинга качества звонков](stream-classification-in-call-quality-dashboard.md)

[Настройка средства аналитики звонков в Skype для бизнеса](set-up-call-analytics.md)

[Использование аналитики звонков для устранения проблем с качеством звонка](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Аналитика звонков и панель мониторинга качества звонков](./monitor-call-quality-qos.md)
