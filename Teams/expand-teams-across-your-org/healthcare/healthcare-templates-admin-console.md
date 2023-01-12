---
title: Использование шаблонов команд для здравоохранения
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Узнайте, как управлять шаблонами команд для здравоохранения и использовать их в Центре администрирования Teams и с помощью Microsoft Graph для быстрого и простого создания команд для вашей организации здравоохранения.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778969"
---
# <a name="use-healthcare-team-templates"></a>Использование шаблонов команд для здравоохранения

С помощью шаблонов команд в Microsoft Teams можно быстро и легко создавать команды с готовой командной структурой параметров, каналов и предустановленных приложений.

В организациях здравоохранения шаблоны команд могут быть особенно полезны, так как они помогают быстро развернуть согласованные команды в организации. Шаблоны также помогают сотрудникам понять, как эффективно использовать Teams.

Teams содержит шаблоны, разработанные специально для организаций здравоохранения. Эти готовые шаблоны можно использовать с целью быстрого создания команд для общения и взаимодействия сотрудников при уходе за пациентами или в ходе работы. В этой статье вы познакомитесь с каждым шаблоном и рекомендуемыми способами их использования.

Способ использования шаблонов команд и управления ими зависит от того, являетесь ли вы администратором или разработчиком.

|Если вы: | Вы можете: |
| ---- | --------- |
| Администратор или ИТ-специалист |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Разработчик | [Использовать Microsoft Graph](#use-team-templates-with-microsoft-graph) для создания команд из шаблонов. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Управление шаблонами команд в Центре администрирования Teams

Как администратор вы можете управлять шаблонами команд в Центре администрирования Microsoft Teams. Здесь можно просмотреть подробные сведения о каждом шаблоне. Вы также можете [создавать и назначать политики шаблонов](../../templates-policies.md) сотрудникам, чтобы управлять тем, какие шаблоны они видят в Teams [для создания команд](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами команд в Центре администрирования Teams](../../get-started-with-teams-templates-in-the-admin-console.md).

В настоящее время предлагаются следующие готовые шаблоны команд для здравоохранения. Чтобы просмотреть их, в левой области навигации Центра администрирования Teams выберите **Команды** > **Шаблоны команд**.

### <a name="patient-care"></a>Уход за пациентами

Упорядочение обмена медицинской информацией и сотрудничества в отделениях, отделах и палатах больниц. Используйте этот шаблон для облегчения ведения пациентов и удовлетворения операционных потребностей палаты. Например, можно опубликовать объявление для отделения в канале *Объявления* и управлять сменами в канале *Персонал*.

>[!div class="mx-tdBreakAll"]
>| Тип шаблона |TemplateId| Свойства этого шаблона |
>| ------------------ |---|----------------------------------------------------- |
>| Уход за пациентами |`healthcareWard` | Каналы:<ul><li>Общий</li><li>Объявления</li><li>Совещания</li><li>Обходы</li><li>Персонал</li><li>Обучение</li></ul> Приложения: <ul><li>Утверждения</li><li>Бюллетени</li><li>Проверка</li><li>Списки</li><li>Смены</li><li>Задачи планировщика и задачи</li><li>Вики</li></ul>|

### <a name="hospital"></a>Больница

Упорядочение обмена информацией и сотрудничества между несколькими отделениями, отделами и палатами в пределах одной больницы. Этот шаблон включает набор каналов для работы больниц. Шаблон можно расширять для дополнительной настройки.

>[!div class="mx-tdBreakAll"]
>| Тип шаблона |TemplateId | Свойства этого шаблона |
>| ------------------|-- |----------------------------------------------------- |
>|Больница|`healthcareHospital`|Каналы: <ul><li>Общий</li><li>Объявления</li><li>Соответствие требованиям</li></li><li>Госпитализация</li><li>Кадры</li><li>Аптека</li></ul>  Приложения: <ul><li>Утверждения</li><li>Бюллетени</li><li>Идеи сотрудников</li><li>Проверка</li><li>Списки</li><li>Смены</li><li>Задачи планировщика и задачи</li><li>Вики</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Использование шаблонов команд с помощью Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

Ниже представлены готовые шаблоны команд для здравоохранения.

### <a name="patient-care"></a>Уход за пациентами

Этот шаблон предназначен для обмена информацией и взаимодействия в отделениях, отделах и палатах больниц. Используйте этот шаблон для облегчения ведения пациентов и удовлетворения операционных потребностей палаты. Например, объявления в отделении больницы можно публиковать в канале *Объявления*, а для управления рабочими сменами можно использовать канал *Персонал*. Этот шаблон пригодится вам, если нужно упорядочить работу отделения больницы.

>[!div class="mx-tdBreakAll"]
>|Тип шаблона |TemplateId |Каналы шаблона|
>|:--- |:---|:---|
>|Здравоохранение — отделение | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | Общий<br>Объявления&sup2; <br> Совещания&sup2; <br> Обходы&sup2; <br> Персонал&sup2; <br> Обучение&sup2; |

&sup2;Автоматически добавленные в избранное каналы

### <a name="hospital"></a>Больница

Этот шаблон предназначен для обмена информацией и взаимодействия между несколькими отделениями, отделами и палатами в пределах одной больницы. Он включает в себя несколько операционных каналов, *таких как Объявления*, *Хранение* и *Фармация*. Мы также предоставляем скрипт, который можно использовать для расширения шаблона с помощью дополнительных отделов или специализированных каналов. Вы можете отредактировать его под свои потребности.

Например, если у вас есть отделение *эндокринологии* , но вам не нужен канал для *офтальмологии*, вы можете адаптировать сценарий, чтобы включить канал *эндокринологии* и удалить канал *Ophthalmology* . Рекомендуем отключить автоматическое добавление в избранное таких каналов, созданных для определенных отделений и специализаций, чтобы избежать получения чрезмерного количества уведомлений. Пользователи обычно заносят в избранное все каналы, которые они считают важными.

>[!div class="mx-tdBreakAll"]
>|Тип шаблона |TemplateId |Каналы шаблона|
>|:--- |:---|:---|
>|Здравоохранение — больница | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | Общий<br>Объявления&sup2; <br> Соответствие требованиям&sup2; <br> Госпитализация <br> Кадры <br> Аптека |

&sup2;Автоматически добавленные в избранное каналы

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Как использовать шаблоны команд с помощью Microsoft Graph

Чтобы использовать эти шаблоны, измените свойство template@odata.bind в тексте запроса со "standard" на "TemplateIds", указанные выше. Дополнительные сведения о развертывании шаблонов команд см. в статье Microsoft Graph о [создании команд](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Каналы в шаблоне будут автоматически созданы на вкладке **Общий**.

#### <a name="example-hospital-template-extension-script"></a>Пример: сценарий расширения шаблона для больниц

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

### <a name="related-articles"></a>Статьи по теме

- [Создание команды на основе шаблона](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Начало работы с шаблонами команд в Центре администрирования Teams](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Начало работы с шаблонами команд с помощью Microsoft Graph](../../get-started-with-teams-templates.md)
- [Начало работы с Teams для организаций в сфере здравоохранения](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)