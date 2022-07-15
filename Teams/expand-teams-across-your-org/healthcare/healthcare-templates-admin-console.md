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
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Узнайте, как управлять шаблонами команд для здравоохранения и использовать их в Центре администрирования Teams и с помощью Microsoft Graph для быстрого и простого создания команд для вашей организации здравоохранения.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 831e4e257277ce2fca6dc007ac5f3bfe963bca35
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819444"
---
# <a name="use-healthcare-team-templates"></a>Использование шаблонов команд для здравоохранения

С помощью шаблонов команд в Microsoft Teams можно быстро и легко создавать команды с готовой командной структурой параметров, каналов и предустановленных приложений.

В организациях здравоохранения шаблоны команд могут быть особенно полезны, так как они помогают быстро развернуть согласованные команды в организации. Шаблоны также помогают сотрудникам понять, как эффективно использовать Teams.

Teams содержит шаблоны, разработанные специально для организаций здравоохранения. Эти готовые шаблоны можно использовать с целью быстрого создания команд для общения и взаимодействия сотрудников при уходе за пациентами или в ходе работы. В этой статье вы познакомитесь с каждым шаблоном и рекомендуемыми способами их использования.

Способ использования шаблонов команд и управления ими зависит от того, являетесь ли вы администратором или разработчиком.

|Если вы: | Вы можете: |
| ---- | --------- |
| Администратор или ИТ-специалист |[Управление шаблонами команд в центре администрирования Teams](#manage-team-templates-in-the-teams-admin-center). Просмотр шаблонов команд и применение политик шаблонов для управления тем, какие шаблоны ваши сотрудники могут использовать в Teams для создания команд. |
| Разработчик | [Использовать Microsoft Graph](#use-team-templates-with-microsoft-graph) для создания команд из шаблонов. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Управление шаблонами команд в Центре администрирования Teams

Как администратор вы можете управлять шаблонами команд в Центре администрирования Microsoft Teams. Здесь можно просмотреть подробные сведения о каждом шаблоне. Вы также можете [создавать и назначать политики шаблонов](../../templates-policies.md) сотрудникам, чтобы управлять тем, какие шаблоны они видят в Teams [для создания команд](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами команд в Центре администрирования Teams](../../get-started-with-teams-templates-in-the-admin-console.md).

В настоящее время предлагаются следующие готовые шаблоны команд для здравоохранения. Чтобы просмотреть их, в левой области навигации Центра администрирования Teams выберите **Команды** > **Шаблоны команд**.
### <a name="patient-care"></a>Уход за пациентом

 Этот шаблон предназначен для обмена информацией и взаимодействия в отделениях, отделах и палатах больниц. Вы можете использовать этот шаблон для упрощения ухода за пациентом и оперативных потребностей отделения. Например, можно опубликовать объявление для отделения в канале *Объявления* и управлять сменами в канале *Персонал*.

| Тип шаблона |TemplateId| Свойства этого шаблона |
| ------------------ |---|----------------------------------------------------- |
| Уход за пациентом |`healthcareWard` | Каналы:<ul><li>Общий</li><li>Объявления<ul><li>Бюллетени&sup1;</li></ul></li><li>Совещания<ul><li>Списки (список пациентов)&sup1;</li></ul></li><li>Обходы<ul><li>Проверка&sup1;</li></ul></li><li>Персонал</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Списки</li><li>Задачи</li><li>Утверждения</li><li>Смены</li><li>Бюллетени</li><li>Проверка</li></ul>|
||||

&sup1;Приложение, добавленное в канал в виде вкладки
### <a name="hospital"></a>Больница

Этот шаблон предназначен для обмена информацией и взаимодействия между несколькими отделениями, отделами и палатами в пределах одной больницы. Этот шаблон включает набор каналов для работы больниц. Шаблон можно расширять для дополнительной настройки.

| Тип шаблона |TemplateId | Свойства этого шаблона |
| ------------------|-- |----------------------------------------------------- |
|Больница|`healthcareHospital`|Каналы: <ul><li>Общий<ul><li>Списки&sup1;</li></ul></li><li>Объявления<ul><li>Бюллетени&sup1;</li></ul></li><li>Соответствие требованиям</li><ul><li>Проверка&sup1;</li></ul></li><li>Госпитализация</li><li>Кадры<ul><li>Идеи&sup1;</li></ul></li><li>Аптека</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li><li>Списки</li><li>Утверждения</li><li>Смены</li><li>Бюллетени</li><li>Проверка</li><li>Идеи</li></ul>|
||||

&sup1;Приложение, добавленное в канал в виде вкладки
## <a name="use-team-templates-with-microsoft-graph"></a>Использование шаблонов команд с помощью Microsoft Graph

Разработчики могут использовать Microsoft Graph для создания команд на основе готовых шаблонов команд. Дополнительные сведения об использовании шаблонов команд с помощью Microsoft Graph см. в статьях [Начало работы с шаблонами команд с помощью Microsoft Graph](../../get-started-with-teams-templates.md), [Обзор API Microsoft Teams](/graph/teams-concept-overview) и [Тип ресурса teamsTemplate](/graph/api/resources/teamstemplate).

Ниже представлены готовые шаблоны команд для здравоохранения.
### <a name="ward"></a>Отделение

Шаблон для отделений предназначен для обмена информацией и взаимодействия в отделениях, отделах и палатах больниц. Этот шаблон можно использовать для ухода за пациентами и выполнения повседневных задач в отделениях больниц. Например, объявления в отделении больницы можно публиковать в канале *Объявления*, а для управления рабочими сменами можно использовать канал *Персонал*. Этот шаблон пригодится вам, если нужно упорядочить работу отделения больницы.

|Тип шаблона |TemplateId |Каналы шаблона|
|:--- |:---|:---|
|Здравоохранение — отделение | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Общий<br>Объявления&sup2; <br> Совещания&sup2; <br> Обходы&sup2; <br> Персонал&sup2; <br> Обучение&sup2; |
|     | |         |

&sup2;Автоматически добавленные в избранное каналы

### <a name="hospital"></a>Больница

Шаблон для больниц предназначен для обмена информацией и взаимодействия между несколькими отделениями, отделами и палатами в пределах одной больницы. Этот шаблон содержит несколько рабочих каналов, например *Объявления*, *Хранитель* и *Аптека*. Мы также предоставляем сценарий, который можно использовать для расширения шаблона дополнительными отделами или специализированными каналами. Вы можете отредактировать его под свои потребности.

Например, если в больнице есть отделение *эндокринологии*, но не нужен канал для *офтальмологии*, можно настроить сценарий, включив в него канал *Эндокринология* и удалив канал *Офтальмология*. Рекомендуем отключить автоматическое добавление в избранное таких каналов, созданных для определенных отделений и специализаций, чтобы избежать получения чрезмерного количества уведомлений. Пользователи обычно заносят в избранное все каналы, которые они считают важными.

|Тип шаблона |TemplateId |Каналы шаблона|
|:--- |:---|:---|
|Здравоохранение — больница | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Общий<br>Объявления&sup2; <br> Соответствие требованиям&sup2; <br> Госпитализация <br> Кадры <br> Аптека |
| | |  |

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