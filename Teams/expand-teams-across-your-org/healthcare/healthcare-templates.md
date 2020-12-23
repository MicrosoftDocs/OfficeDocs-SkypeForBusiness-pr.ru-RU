---
title: Шаблоны для медицинских организаций
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Используйте шаблоны Microsoft Teams с Microsoft Graph для быстрого и простого создания команд, предоставляя предопределенный шаблон настроек, каналов и приложений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4c2e10efbff98150b120d1c026d4d810629333f2
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790411"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Начало работы с шаблонами Teams для медицинских организаций

Шаблоны Microsoft Teams позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон настроек, каналов и предварительно установленных приложений.

В медицинских организациях шаблоны могут быть особенно эффективны, так как они обеспечивают структуру для пользователей, чтобы ориентироваться в том, как эффективно использовать Teams. Шаблоны также позволяют администраторам развертывать согласованные группы в организации. Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации здравоохранения.

В настоящее время мы предлагаем два шаблона для здравоохранения, которые можно использовать в различных ситуациях. Подробнее о шаблонах команд см. в шаблонах [Teams.](../../get-started-with-teams-templates.md)

## <a name="ward-template"></a>Шаблон шаблона "Шаблон шаблона"

Шаблон шаблона предназначен для общения и совместной работы в рамках одного из отделов, pod или отделов. Шаблон можно использовать для упрощения управления пациентом, а также для оперативных потребностей человека. Например, в канале "Извещающие" можно размещать объявления, а сменами можно управлять в области  "Персонал".  Если вы хотите упростить свою операцию, этот шаблон вам по-настоящему упорядочен.

|Тип базового шаблона |baseTemplateId |Каналы шаблонов базовых показателей|
|:--- |:---|:---|
|Здравоохранение — Сша | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Объявления\* <br> Huddles\* <br> Округ округит\* <br> Персонал\* <br> Обучение\* |
|     | |         |

\* Автоматическое избранное

## <a name="hospital-template"></a>Шаблон для больнице

Шаблон для управления больницей предназначен для общения и совместной работы между несколькими ее отделами, pods и другими отделами. В этот шаблон входит несколько рабочих каналов, включая "Объявления", "Хранитель" и "Хранитель", но также предлагается сценарий, который расширяет шаблон с разнообразными дополнительными каналами для работы со специализированными сайтами, которые можно добавлять, удалять или редактировать по своему вкусу.  Например, если у вас есть отдел *endocrinology,* но для *Ophthalmology* не нужен канал, сценарий можно адаптировать, чтобы включить канал *endocrinology* и удалить канал *Ophthalmology.* Мы рекомендуем не использовать эти специализированные каналы в автоматическом избранном, чтобы избежать насыщенности уведомлений. Как правило, пользователи избранные каналы, которые им важны.

|Тип базового шаблона |baseTemplateId |Каналы шаблонов базовых показателей|
|:--- |:---|:---|
|Здравоохранение — больнице | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Объявления\* <br> Соответствие требованиям\* <br> Хранитель <br> Человеческие ресурсы <br> Веха |
| | |  |

\* Автоматическое избранное 

## <a name="how-to-use-first-party-templates"></a>Использование шаблонов сторонних шаблонов

Чтобы использовать эти шаблоны, просто измените свойство template@odata.bind в теле запроса со стандартного на шаблон TemplateIDs выше.  Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о том, как [создать команду.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Каналы в шаблоне будут автоматически созданы на вкладке "Общие".

### <a name="example-hospital-template-extension-script"></a>Пример: сценарий расширения шаблона в больнице

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

[Начало работы с шаблонами Teams в консоли администрирования](../../get-started-with-teams-templates-in-the-admin-console.md)
