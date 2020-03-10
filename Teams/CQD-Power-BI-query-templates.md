---
title: Анализ данных CQD в Microsoft Teams с помощью Power BI
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Проанализируйте данные CQD в Microsoft Teams с помощью Power BI.
ms.openlocfilehash: 155bde0373880befc770d745ca246b76d4c63eec
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572897"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Анализ данных CQD в Microsoft Teams с помощью Power BI

Новые возможности в январе 2020: [Скачайте шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые шаблоны Power BI, которые можно использовать для анализа и составления отчетов о CQD данных.

Если вы хотите использовать Power BI для запроса и создания отчетов о ваших данных, скачайте CQD шаблоны Power BI для CQD. Когда вы открываете шаблоны в Power BI, вам будет предложено выполнить вход с учетными данными администратора CQD. Вы можете настроить эти шаблоны запросов и распространить их среди всех пользователей в Организации, у которых есть лицензия на Power BI и разрешения администратора CQD.

Прежде чем вы сможете использовать эти PBIX-файлы, необходимо [установить соединитель Power BI для Microsoft CQD](CQD-Power-BI-connector.md) с помощью файла *микрософткаллкуалити. пккс* , который входит в комплект [загрузки](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


|  |  |
|---------|---------|
|CQD Reporting служба поддержки. pbix     |Интеграция создания и ЕУИИ данных. Этот отчет предназначен для того, чтобы перейти от одного пользователя к переходу к воспроизведению корневой причины слабого звонка для этого пользователя (например, если пользователь находится в процессе построения, в котором возникли проблемы с сетью).         |
|CQD расположение Enhanced Report. pbix     | Повторное создание CQDных отчетов о расположении SPD. Включает 9 отчетов, обеспечивая качество связи, создание WiFi, надежность и оценку сведений о звонке (РМК) с дополнительными переходами, а также с помощью пользователей.        |
|CQD мобильного устройства Report. pbix     | Предоставляет аналитические сведения, специально настроенные для пользователей мобильных устройств, в том числе качество связи, надежность и скорость звонка. Просмотр отчетов мобильной сети, сетей Wi-Fi и мобильных операционных систем (Android, iOS).        |
|CQD КТСОП прямая маршрутизация. pbix     |Предоставляет аналитические сведения, специфичные для КОММУТИРУЕМых звонков, которые проходят через прямую маршрутизацию. Для получения дополнительных сведений ознакомьтесь с разделом [Использование прямого маршрута CQD КТСОП](CQD-PSTN-report.md).         |
|Сводный отчет CQD. pbix     |Улучшенные зрительные образы, повышенная презентация, повышенная плотность данных и даты их пошагового применения. Эти отчеты упрощают создание идентификаторов выбросов. Обобщение по качеству звонка с помощью удобной интерактивной карты. 9 новых отчетов:</p>-Общее качество<br>-Общая надежность<br>-РМК (оценить мой звонок) всего<br>-Качество конференции<br>-P2P качество<br>-Надежность конференции<br>-P2P надежность<br>-РМК конференции<br>-P2P РМК         |
|<strong>(New!)</strong> CQD Teams Report использование. pbix     | Показывает, как пользователи в вашей организации используют команды и сколько. Подробнее читайте в статье [Использование отчета Power BI в CQD для просмотра использования Microsoft Teams](CQD-teams-utilization-report.md).        |
|CQD Отзывы пользователей (оценивать мой звонок) Report. pbix     | Сведения о звонках, которые можно легко использовать для поддержки звонков в Организации. Перекрестные ссылки с помощью точной рекламы для идентификации возможностей образования для конечных пользователей.        |


## <a name="related-topics"></a>Статьи по теме

[Измерения и меры на панели мониторинга качества звонков](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков на панели мониторинга качества звонков](stream-classification-in-call-quality-dashboard.md)

[Настройка средства аналитики звонков в Skype для бизнеса](set-up-call-analytics.md)

[Использование аналитики звонков для устранения проблем с качеством звонка](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Аналитика звонков и панель мониторинга качества звонков](difference-between-call-analytics-and-call-quality-dashboard.md)
 