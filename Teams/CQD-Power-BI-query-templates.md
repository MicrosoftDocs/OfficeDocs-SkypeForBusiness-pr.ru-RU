---
title: Используйте Power BI для анализа данных CQD для Microsoft Teams
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
ms.openlocfilehash: 7314a0fb4a5bd1058e2270a3302e165eacc05d07dca4ebcc599a75aed687cd74
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286238"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Используйте Power BI для анализа данных CQD для Microsoft Teams

Новое в январе 2020 г.: [скачивание шаблонов Power BI запросов для CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.

Если вы хотите использовать Teams для запросов и отчетов о своих данных с помощью Power BI, скачайте наши шаблоны панели мониторинга качества Power BI звонка. Когда вы откроете шаблоны в Power BI, вам будет предложено войти с учетными данными администратора CQD. Вы можете настроить эти шаблоны запросов и распространить их всем в организации, у которых есть Power BI лицензии и разрешения администратора CQD.

Прежде чем использовать эти PBIT-файлы, необходимо установить Power BI Connector для [Microsoft CQD](CQD-Power-BI-connector.md) с помощью файла *MicrosoftCallQuality.pqx,* включенного в скачаемый [файл](https://www.microsoft.com/download/details.aspx?id=102291). 

Убедитесь, что у вас есть права на доступ к отчетам Power BI [CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 

|  |  |
|---------|---------|
|<strong>(Новый!)</strong> CQD Teams auto Attendant & queue queue Report.pbit     |  Этот шаблон содержит три отчета:</p><li>Автоответ: отображение аналитики для звонков, которые будут приходить в ваш автоответ.</li><li>Очередь звонков— отображение аналитики для звонков, которые будут приходить в очереди звонков.</li><li>Временная шкала агента— отображение временной шкалы, в которой агенты активны во время звонков в очереди звонков.</li><br>Подробнее об этом можно узнать в & истории & [очереди вызовов.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |Интегрирование здания и данных EUII. Этот отчет предназначен для того, чтобы вы могли получить данные от одного пользователя, чтобы найти причину низкого качества звонка для этого пользователя (например, пользователь находится в здании, в которое возникли проблемы с сетью).         |
|CQD Location Enhanced Report.pbit     | Повторное вложение отчетов о расположении CQD с SPD. Включает 9 отчетов, включающих сведения о качестве звонка, построении Wi-Fi, надежности и ставке звонка (RMC), с дополнительными данными drill-thrus по зданиям или по пользователям.  Убедитесь, что вы загрузили данные о здании, чтобы максимально эффективно использовать отчеты.        |
|CQD Mobile Device Report.pbit     | Предоставляет сведения, специально настроенные для пользователей мобильных устройств, в том числе качество звонка, надежность и оценить мой звонок. Просмотр отчетов о мобильной сети, сети Wi-Fi и операционных системах для мобильных устройств (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Предоставляет сведения о звонках по ННР, которые проходят прямую маршрутику. Подробнее об этом можно узнать в отчете О прямой маршрутике по [ПСДН.](CQD-PSTN-report.md)         |
|CQD Summary Report.pbit     |Улучшенные визуализации, улучшенная презентация, повышенная плотность данных и даты вкатывания. Эти отчеты упрощают определение выбросов. С помощью удобной интерактивной карты можно отсверлить качество звонка по расположению. 9 новых отчетов:</p>- Общее качество<br>- Надежность в целом<br>- RMC (Rate My Call) Overall<br>Качество конференции<br>Качество P2P<br>Надежность конференции<br>Надежность P2P<br>- Conference RMC<br>- P2P RMC         |
|<strong>(Новый!)</strong> CQD Teams Использование Report.pbit     | Показывает, как пользователи в вашей организации используют Teams и в какой степени. Убедитесь, что вы загрузили данные о здании, чтобы максимально эффективно использовать отчеты. Подробнее об этом можно узнать в Power BI [CQD для просмотра](CQD-teams-utilization-report.md)Microsoft Teams использования.        |
|CQD User Feedback (Rate My Call) Report.pbit     | Показывает оцените данные моих звонков таким образом, чтобы вы могли легко использовать их для поддержки звонков в организации. Перекрестная ссылка с глаголами для определения возможностей обучения конечных пользователей.        |

> [!TIP]
> После того как вы настроите отчеты Power BI данных CQD, добавьте их в качестве вкладки в канал. Выбрав **+** канал, выберите Power BI  и найдите отчет. Подробнее см. в документе Отчет о встраии в Power BI [для Teams.](/power-bi/service-embed-report-microsoft-teams) Помните, что доступ к этим отчетам могут получить только люди с Power BI лицензией и учетными данными администратора CQD.


## <a name="related-topics"></a>Статьи по теме

[Измерения и меры на панели мониторинга качества звонков](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков на панели мониторинга качества звонков](stream-classification-in-call-quality-dashboard.md)

[Настройка средства аналитики звонков в Skype для бизнеса](set-up-call-analytics.md)

[Использование аналитики звонков для устранения проблем с качеством звонка](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Аналитика звонков и панель мониторинга качества звонков](./monitor-call-quality-qos.md)
