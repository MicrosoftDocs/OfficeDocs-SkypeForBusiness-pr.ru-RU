---
title: Начало работы с шаблонами Teams для организаций в сфере здравоохранения
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Начало работы с шаблонами Teams для организаций в сфере здравоохранения
ms.openlocfilehash: 437a645a0ab32024e81f3c73ba0db09b08267b3d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232254"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Начало работы с шаблонами Teams для организаций в сфере здравоохранения

Шаблоны Microsoft Teams позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.

Для организаций здравоохранения шаблоны могут быть особенно мощными, так как они предоставляют структуру для пользователей, с помощью которых лучше эффективно использовать команды. Шаблоны также позволяют администраторам развертывать единообразные команды для разных организаций. Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в организации здравоохранения.

В настоящее время мы предлагаем два шаблона здравоохранения для первого производителя, которые можно использовать в различных ситуациях. Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп](../../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Шаблон "на"

Шаблон "один" предназначен для общения и совместной работы в любом приложении, Pod или отделе. Шаблон можно использовать для упрощения управления пациентами, а также для выполнения производственных задач. Например, в каналах *извещений* и сменах могут быть опубликованы дополнительные объявления. ** Если вы хотите упростить выполнение операций, выберите этот шаблон.

|Тип базового шаблона |басетемплатеид |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение – до | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Обслуживании\* <br> худдлес\* <br> До\* <br> Штата\* <br> Подготовку\* |
|     | |         |

\*Автоматическое добавление в избранное

## <a name="hospital-template"></a>Шаблон больницы

Шаблон больницы предназначен для общения и совместной работы между несколькими приложениями, многими из них и подразделениями в рамках больницы. В этот шаблон включены несколько рабочих каналов, включая *извещения*, *кустодиал*и *фармаци*, но Кроме того, мы предоставляем ниже сценарий, который расширяет шаблон с помощью разнообразных дополнительных отделов или ориентированные на специальные каналы, которые можно добавлять, удалять и изменять. Например, если у вас есть отдел *ендокринологи* , но не нужен канал для *офсалмологи*, сценарий можно адаптировать для включения канала *ендокринологи* и удаления канала *офсалмологи* . Рекомендуется, чтобы эти специальные или Многомодельные каналы не были автоматически избраны для предотвращения насыщенности уведомлений. Пользователи обычно используют любые каналы, которые им нужны.

|Тип базового шаблона |басетемплатеид |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение – больницы | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Обслуживании\* <br> О\* <br> кустодиал <br> Человеческие ресурсы <br> фармаци |
| | |  |

\*Автоматическое добавление в избранное 

## <a name="how-to-use-first-party-templates"></a>Использование шаблонов первого субъекта

Чтобы использовать эти шаблоны, просто измените свойство "template@odata.bind" в теле запроса с "Standard" на Темплатеидс выше.  Дополнительные сведения о том, как развертывать шаблоны групп, можно найти в [статье Microsoft Graph о создании группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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
              "displayName": "Women’s Health",
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
