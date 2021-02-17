---
title: Создание команды с помощью шаблонов Teams для здравоохранения
author: cichur
ms.author: v-cichur
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
description: Используйте шаблоны Microsoft Teams в Центре администрирования или с Microsoft Graph, чтобы быстро и легко создавать команды, предоставляя предопределенный шаблон параметров, каналов и приложений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260311"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Создание команды с помощью шаблонов Teams для здравоохранения

Шаблоны Microsoft Teams позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон настроек, каналов и предварительно установленных приложений.

В медицинских учреждениях шаблоны могут быть особенно эффективными, так как они обеспечивают структуру, которая позволяет пользователям ориентироваться в том, как эффективно использовать Teams. Шаблоны также позволяют администраторам развертывать согласованные группы в организации. Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации здравоохранения.

Выберите способ создания команд с помощью шаблонов Teams для здравоохранения:

| Кто | Метод использования: |
| ---- | --------- |
| Администраторы и ИТ-специалисты | [С помощью Центра администрирования Teams](#use-the-teams-templates-in-the-teams-admin-center) можно создавать команды на основе шаблонов Teams для здравоохранения.|
| Разработчики и интеграторы для систем | [Используйте Microsoft Graph для](#use-the-teams-templates-with-the-microsoft-graph) создания команд на основе шаблонов Teams для здравоохранения. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Использование шаблонов Teams в Центре администрирования Teams

Администраторы Microsoft Teams могут использовать Центр администрирования Teams для создания команд с помощью шаблонов Teams. В настоящее время мы предлагаем два шаблона, которые можно использовать в различных ситуациях. Дополнительные информацию о шаблонах команд см. в шаблонах Teams в [Центре администрирования.](../../get-started-with-teams-templates-in-the-admin-console.md)

### <a name="collaborate-on-patient-care"></a>Совместное обслуживание пациентов

 Упростите взаимодействие в сфере здравоохранения и совместную работу в отделе, организации или отделе. Шаблон можно использовать для упрощения управления пациентом и оперативных потребностей человека.

| Тип базового шаблона |baseTemplateId| Свойства, которые доступны с этим базовым шаблоном |
| ------------------ |---|----------------------------------------------------- |
| Совместное обслуживание пациентов |`healthcareWard` | Каналы:<ul><li>Общий</li><li>Объявления</li><li>Huddles</li><li>Округ округит</li><li>Персонал</li><li>Обучение</li></ul> Приложения: <ul><li>Вики-сайт</li><li>Списки</li></ul>|
||||

### <a name="hospital"></a>Больница

Упростите взаимодействие и совместную работу между несколькими отделами, pods и отделами в больнице. Этот шаблон содержит набор базовых каналов для работы в больнице, и его можно самостоятельно включить в него специальные каналы, специальные каналы.

| Тип базового шаблона |baseTemplateId | Свойства, которые доступны с этим базовым шаблоном |
| ------------------|-- |----------------------------------------------------- |
|Больница|`healthcareHospital`|Каналы: <ul><li>Общий</li><li>Объявления</li><li>Соответствие требованиям</li><li>Хранитель</li><li>Человеческие ресурсы</li><li>Веха</li></ul> Приложения: <ul><li>Вики-сайт</li><li>Списки </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Использование шаблонов Teams с Microsoft Graph

Разработчики могут использовать Microsoft Graph для создания команд с помощью шаблонов Teams. В настоящее время мы предлагаем два шаблона, которые можно использовать в различных ситуациях. Подробнее о шаблонах команд см. в шаблонах [Teams.](../../get-started-with-teams-templates.md) Сведения о шаблонах Teams и Microsoft Graph см. в обзоре [API Microsoft Teams](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) и типе [ресурсов TeamsTemplate.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)

### <a name="ward-template"></a>Шаблон с шаблоном "Шаблон с шаблон

Шаблон шаблона шаблона шаблона предназначен для общения и совместной работы в рамках одного из отделов, pod или отделов. Шаблон можно использовать для упрощения управления пациентом, а также для оперативных потребностей человека. Например, в канале "Извещающие" можно размещать объявления, а сменами можно управлять в области  "Персонал".  Если вы хотите упростить свою операцию по операции, этот шаблон для вас.

|Тип базового шаблона |baseTemplateId |Каналы шаблона базового плана|
|:--- |:---|:---|
|Здравоохранение — Скайб | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Объявления\* <br> Huddles\* <br> Округ округит\* <br> Персонал\* <br> Обучение\* |
|     | |         |

\* Автоматическое избранное

### <a name="hospital-template"></a>Шаблон для больнице

Шаблон для управления больницей предназначен для общения и совместной работы между несколькими двумя другими людьми: например, в больнице есть несколько разных отделов и отделов. В этот шаблон входит несколько рабочих каналов, включая "Объявления", "Хранитель" и "Хранитель", но ниже предлагается сценарий, который расширяет шаблон с разнообразными дополнительными каналами для работы со специализированными сайтами, которые можно добавлять, удалять или редактировать по своему вкусу.  Например, если у вас есть отдел *endocrinology,* но для *Ophthalmology* не нужен канал, сценарий можно адаптировать, чтобы включить канал *endocrinology* и удалить канал *Ophthalmology.* Рекомендуется не использовать эти специализированные каналы в автоматическом избранном, чтобы избежать насыщенности уведомлений. Как правило, пользователи избранные каналы, которые им важны.

|Тип базового шаблона |baseTemplateId |Каналы шаблона базового плана|
|:--- |:---|:---|
|Здравоохранение — больнице | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Объявления\* <br> Соответствие требованиям\* <br> Хранитель <br> Человеческие ресурсы <br> Веха |
| | |  |

\* Автоматическое избранное 

### <a name="how-to-use-first-party-templates"></a>Использование шаблонов сторонних шаблонов

Чтобы использовать эти шаблоны, просто измените свойство template@odata.bind в теле запроса со стандартного на шаблон TemplateIDs выше.  Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о том, как [создать команду.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Каналы в шаблоне будут автоматически созданы на вкладке "Общие".

#### <a name="example-hospital-template-extension-script"></a>Пример: сценарий расширения шаблона в больнице

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

### <a name="related-topics"></a>Статьи по теме

[Начало работы с шаблонами Teams](../../get-started-with-teams-templates.md)

[Начало работы с Teams для организаций в сфере здравоохранения](teams-in-hc.md)
