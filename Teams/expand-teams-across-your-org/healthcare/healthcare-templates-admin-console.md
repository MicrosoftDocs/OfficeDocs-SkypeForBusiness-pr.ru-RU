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
description: Используйте шаблоны Microsoft Teams в Центре администрирования или в Microsoft Graph, чтобы быстро и удобно создавать команды на основе готовых шаблонов с параметрами, каналами и приложениями.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117877"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Создание команды с помощью шаблонов Teams для здравоохранения

С помощью шаблонов Microsoft Teams можно быстро и удобно создавать команды: готовые шаблоны содержат параметры, каналы и предустановленные приложения.

Шаблоны могут быть особенно эффективными для организаций здравоохранения, поскольку они помогают пользователям научиться эффективнее использовать Teams. Благодаря шаблонам администраторы могут развертывать одинаково устроенные команды в своих организациях. Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в своей организации здравоохранения.

Выберите метод создания команд с помощью шаблонов Teams для здравоохранения:

| Кто | Используемый метод: |
| ---- | --------- |
| Администраторы и ИТ-специалисты | [Используйте Центр администрирования Teams](#use-the-teams-templates-in-the-teams-admin-center) для создания команд на основе шаблонов Teams для здравоохранения.|
| Разработчики и системные интеграторы | [Используйте Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) для создания команд на основе шаблонов Teams для здравоохранения. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Использование шаблонов Teams в Центре администрирования Teams

Администраторы Microsoft Teams могут использовать Центр администрирования Teams для создания команд с помощью шаблонов Teams. В настоящее время мы предлагаем два разработанных нами шаблона для здравоохранения, которые можно использовать в различных ситуациях. Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams в Центре администрирования](../../get-started-with-teams-templates-in-the-admin-console.md).

### <a name="collaborate-on-patient-care"></a>Совместная работа по уходу за пациентами

 Упорядочение обмена медицинской информацией и сотрудничества в отделениях, отделах и палатах больниц. Этот шаблон можно использовать для управления пациентами и для выполнения повседневных задач в отделениях больниц.

| Тип базового шаблона |baseTemplateId| Свойства базового шаблона |
| ------------------ |---|----------------------------------------------------- |
| Совместная работа по уходу за пациентами |`healthcareWard` | Каналы:<ul><li>Общие</li><li>Объявления</li><li>Совещания</li><li>Обходы</li><li>Персонал</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Списки</li></ul>|
||||

### <a name="hospital"></a>Больница

Упорядочение обмена информацией и сотрудничества между несколькими отделениями, отделами и палатами в пределах одной больницы. Этот шаблон включает набор базовых каналов для работы больниц. Шаблон можно произвольно расширять для добавления специализаций.

| Тип базового шаблона |baseTemplateId | Свойства базового шаблона |
| ------------------|-- |----------------------------------------------------- |
|Больница|`healthcareHospital`|Каналы: <ul><li>Общие</li><li>Объявления</li><li>Соответствие требованиям</li><li>Госпитализация</li><li>Кадры</li><li>Аптека</li></ul> Приложения: <ul><li>Вики</li><li>Списки </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Использование шаблонов Teams с Microsoft Graph

Разработчики могут использовать Microsoft Graph для создания команд с помощью шаблонов Teams. В настоящее время мы предлагаем два разработанных нами шаблона для здравоохранения, которые можно использовать в различных ситуациях. Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](../../get-started-with-teams-templates.md). Сведения о шаблонах Teams и Microsoft Graph, см. в статьях [Обзор API Microsoft Teams API](/graph/teams-concept-overview?view=graph-rest-1.0) и [Тип ресурса teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="ward-template"></a>Шаблон для отделений больницы

Шаблон для отделений предназначен для обмена информацией и сотрудничества в отделениях, отделах и палатах больниц. Этот шаблон можно использовать для управления пациентами и для выполнения повседневных задач в отделениях больниц. Например, объявления в отделении больницы можно публиковать в канале *Объявления*, а для управления рабочими сменами можно использовать канал *Персонал*. Этот шаблон пригодится вам, если нужно упорядочить работу отделения больницы.

|Тип базового шаблона |baseTemplateId |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение — отделение | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Объявления\* <br> Совещания\* <br> Обходы\* <br> Персонал\* <br> Обучение\* |
|     | |         |

Автоматическое избранное: \*

### <a name="hospital-template"></a>Шаблон для больниц

Шаблон для больниц предназначен для обмена информацией и сотрудничества между несколькими отделениями, отделами и палатами в пределах одной больницы. Этот шаблон включает несколько рабочих каналов, в том числе *Объявления*, *Госпитализация* и *Аптека*. Кроме того, мы предоставляем указанный ниже сценарий, дающий возможность расширить шаблон, добавив в него ряд дополнительных каналов для определенных отделений или специализаций. Вы сможете добавлять такие каналы, удалять и редактировать их по вашему усмотрению. Например, если в больнице есть отделение *эндокринологии*, но не нужен канал для *офтальмологии*, можно настроить сценарий, включив в него канал *Эндокринология* и удалив канал *Офтальмология*. Рекомендуем отключить автоматическое добавление в избранное таких каналов, созданных для определенных отделений и специализаций, чтобы избежать получения чрезмерного количества уведомлений. Пользователи обычно заносят в избранное все каналы, которые они считают важными.

|Тип базового шаблона |baseTemplateId |Каналы базового шаблона|
|:--- |:---|:---|
|Здравоохранение — больница | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Объявления\* <br> Соответствие требованиям\* <br> Госпитализация <br> Кадры <br> Аптека |
| | |  |

Автоматическое избранное: \* 

### <a name="how-to-use-first-party-templates"></a>Использование собственных шаблонов

Чтобы использовать эти шаблоны, измените значение свойства "template@odata.bind" в тексте запроса со "standard" на указанные выше идентификаторы TemplateID.  Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о [создании команд](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Каналы в шаблоне будут автоматически создаваться на вкладке "Общие".

#### <a name="example-hospital-template-extension-script"></a>Пример: сценарий для расширения шаблона для больниц

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