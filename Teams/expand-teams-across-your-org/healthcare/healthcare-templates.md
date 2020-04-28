---
title: Шаблоны для организаций здравоохранения
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Используйте шаблоны Microsoft Teams, чтобы быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и приложений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: db6475c3d7c4be6242c1befb988b240b9efcab42
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904731"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Начало работы с шаблонами Teams для организаций в сфере здравоохранения

Шаблоны Microsoft Teams позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.

Для организаций здравоохранения шаблоны могут быть особенно мощными, так как они предоставляют структуру для пользователей, с помощью которых лучше эффективно использовать команды. Шаблоны также позволяют администраторам развертывать единообразные команды для разных организаций. Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в организации здравоохранения.

В настоящее время мы предлагаем два шаблона здравоохранения для первого производителя, которые можно использовать в различных ситуациях. Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп](../../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Шаблон "на"

Шаблон "один" предназначен для общения и совместной работы в любом приложении, Pod или отделе. Шаблон можно использовать для упрощения управления пациентами, а также для выполнения производственных задач. Например, в каналах *извещений* и сменах могут быть опубликованы дополнительные *объявления.* Если вы хотите упростить выполнение операций, выберите этот шаблон.

|Тип базового шаблона |baseTemplateId |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение – до | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Обслуживании\* <br> Huddles\* <br> До\* <br> Штата\* <br> Обучение\* |
|     | |         |

\*Автоматическое добавление в избранное

## <a name="hospital-template"></a>Шаблон больницы

Шаблон больницы предназначен для общения и совместной работы между несколькими приложениями, многими из них и подразделениями в рамках больницы. В этот шаблон включены несколько рабочих каналов, включая *извещения*, *custodial*и *Pharmacy*, но мы также предоставляем ниже сценарий, который расширяет шаблон с учетом разнообразных дополнительных подразделений и специальных каналов, которые можно добавлять, удалять и изменять. Например, если у вас есть отдел *Endocrinology* , но не нужен канал для *ophthalmology*, сценарий можно адаптировать для включения канала *Endocrinology* и удаления канала *ophthalmology* . Рекомендуется, чтобы эти специальные или Многомодельные каналы не были автоматически избраны для предотвращения насыщенности уведомлений. Пользователи обычно используют любые каналы, которые им нужны.

|Тип базового шаблона |baseTemplateId |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение – больницы | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Обслуживании\* <br> О\* <br> Custodial <br> Человеческие ресурсы <br> Pharmacy |
| | |  |

\*Автоматическое добавление в избранное 

## <a name="how-to-use-first-party-templates"></a>Использование шаблонов первого субъекта

Чтобы использовать эти шаблоны, просто измените свойство "template@odata. Bind" в теле запроса с "Standard" на TemplateIDs выше.  Дополнительные сведения о развертывании шаблонов групп можно найти в статье Microsoft Graph о том, как [создавать группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Каналы в шаблоне будут автоматически созданы на вкладке "Общие".

### <a name="example-hospital-template-extension-script"></a>Пример: сценарий расширения шаблонов для больницы

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

## <a name="related-topics"></a>Статьи по теме

[Начало работы с шаблонами Teams](../../get-started-with-teams-templates.md)

[Начало работы с Teams для организаций в сфере здравоохранения](teams-in-hc.md)
