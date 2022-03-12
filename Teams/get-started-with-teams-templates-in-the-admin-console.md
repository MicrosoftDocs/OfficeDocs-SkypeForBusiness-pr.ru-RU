---
title: Начало работы с шаблонами команд в Центре администрирования Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте о шаблонах групп и о том, как управлять ими в центре Microsoft Teams администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e65f7a0eef62197e90f77876129af95f32f4d6bc
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442485"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Начало работы с шаблонами команд в Центре администрирования Teams

**Возможность создавать пользовательские шаблоны пока не поддерживается пользователями EDU.**

> [!NOTE]
> - Закрытые каналы в настоящее время не поддерживаются в шаблонах команд. Создание частного канала не включается в определения шаблонов.
>
> - Метки конфиденциальности не поддерживаются в шаблонах группы GCC средах. Параметр метки конфиденциальности в потоке Создание команды из шаблона не применяется к команде.

## <a name="overview"></a>Обзор

Шаблон группы в Microsoft Teams — это определение структуры группы, разработанной для бизнес-потребности или проекта. Как администратор вы можете использовать шаблоны для простого развертывания согласованных групп в организации. С помощью шаблонов пользователи могут быстро создавать форматирование пространства для совместной работы с заранее задав параметры, каналы и приложения.

Вы можете управлять шаблонами групп в Microsoft Teams центре администрирования или с помощью PowerShell. Вы можете использовать встроенные шаблоны, которые мы предоставляем, а также создавать [собственные](#create-your-own-team-templates). Вы также можете [применять политики шаблонов](#apply-team-template-policies) для управления тем, какие шаблоны доступны пользователям в Teams.

В этой статье представлен обзор работы с шаблонами групп в Центре Teams администрирования. Вы узнаете о свойствах, которые поддерживаются в шаблонах, встроенных шаблонах, ограничениях размера шаблонов, о том, как создавать шаблоны и управлять ими, а также о других.

> [!NOTE]
> Пользователи могут [создавать команды из встроенных или](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) настраиваемых шаблонов в Teams приложения. Разработчики также могут программным путем создавать команды из встроенных шаблонов с помощью Microsoft Graph. Дополнительные информации см. в этой ссылке. Начало работы с [шаблонами команд с помощью Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Возможности шаблонов команд

Большинство свойств группы включаются и поддерживаются шаблонами. Но есть несколько свойств и функций, которые в настоящее время не поддерживаются. Вот краткое описание того, что входит в шаблоны команд.

| **Свойства группы, поддерживаемые шаблонами команд** | **Свойства группы пока не поддерживаются шаблонами команд** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Тип шаблона | Участники команды |
| Название команды | Изображение группы |
| Описание группы | Параметры канала |
| Видимость группы (открытой или закрытой) | Соединители |
| Параметры команды (например, упоминания участника, гостя и @) | Файлы и контент |
| Канал autofavorite | |
| Установленное приложение | |
| Закрепленные вкладки | |

> [!NOTE]
> Мы будем добавлять дополнительные возможности шаблонов в будущих выпусках Microsoft Teams, поэтому ознакомьтесь с самой информацией о поддерживаемых свойствах.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Встроенные шаблоны групп в Центре Teams администрирования

Вот готовые шаблоны групп, которые можно найти в центре Teams администрирования. Готовые шаблоны — это шаблоны, созданные для определенных отраслей. Чтобы просмотреть эти шаблоны, в левой области навигации центра администрирования Teams перейдите к **шаблонам Teams** >  **Team**.

Вы можете дублировать встроенные шаблоны, но не редактировать их. Если вы хотите изменить свойства встроенного шаблона, можно создать новый шаблон из существующего, а затем добавить или удалить нужные свойства. Помните, что некоторые свойства некоторых шаблонов изменить нельзя.

| Тип шаблона | TemplateId | Свойства этого шаблона |
| ------------------ | -------------- | ----------------------------------------------------- |
| Принятие Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Угловой угол химок</li> <li>Формы команд</li><li>Календарь</li></ul> Приложения: <ul><li>Вики</li>  <li>Календарь канала</li> <li>Вехи</li><li>Бюллетени</li></ul>|
| Управление проектом |`com.microsoft.teams.template.ManageAProject`| Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Ресурсы</li> <li>Планирование</li></ul> Приложения:<ul><li>Вики</li><li>OneNote</li><li>Задачи</li><li>Списки</li><li>Power Automate</li></ul> |
| Управление событием|`com.microsoft.teams.template.ManageAnEvent` | Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Бюджет</li> <li>Содержимое</li><li>Логистика</li> <li>Планирование</li> <li> Маркетинг и PR</li></ul> Приложения:<ul><li>Вики</li><li>Веб-сайт</li> <li>YouTube</li> <li>Задачи</li> <li>OneNote</li> <li>Идеи сотрудников</li> <li>Сообщающий о проблеме</li><li>Power Automate</li><li>Бюллетени</li><li>Вехи</li></ul> |
|Сотрудники, работающие на доске|`com.microsoft.teams.template.OnboardEmployees` | Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Чат сотрудника</li> <li>Учебный курс</li></ul>Приложения:<ul><li>Вики</li><li>Общин</li><li>Задачи</li><li>Идеи сотрудников</li><li>Power Automate</li><li>Бюллетени</li><li>Вехи</li></ul>|
|Организовать службу поддержки| `com.microsoft.teams.template.OrganizeHelpDesk`|Каналы:<ul><li>Общие</li><li>Объявления</li><li>Вопросы и ответы</li></ul>Приложения:<ul><li>Вики</li><li>OneNote</li><li>Задачи </li><li>Благодарность</li><li>Сообщающий о проблеме</li><li>Power Automate</li><li>Бюллетени</li></ul> |
| Уход за пациентом| `com.microsoft.teams.template.healthcareWard`| Каналы:<ul><li>Общие</li><li>Объявления</li><li>Совещания</li><li>Обходы</li><li>Персонал</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Списки  </li><li>Утверждения</li><li>Бюллетени</li><li>Проверка</li></ul>|
| Связь в связи скрикрибом |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Каналы: <ul><li>Общие<li>Объявления</li><li>World news</li><li>Внутренние запятые</li><li>Внешние запятые</li><li>Запрос на утверждение</li><li>Рост клиентов</li><li>Обновление руководства</li><li>Планирование</li><li>Логистика</li></ul>Приложения: <ul><li>Веб-сайт</li><li>Задачи</li><li>Сообщающий о проблеме</li><li>Утверждения</li><li>Бюллетени</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|Банковский филиал| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Каналы: <ul><li>Общие<li>Объявления</li><li>Совещания</li><li>Встречи с клиентами</li><li>Запрос на утверждение </li><li>Обучение</li><li>Развитие навыков</li><li>Обработка кредитных заявок</li><li>Жалобы клиентов</li><li>Поздравления</li><li>Развлечения</li><li>Соответствие требованиям</li></ul>Приложения:<ul><li>Благодарность </li><li>Сообщающий о проблеме</li><li>Вики</li><li>Календарь</li><li>Утверждения</li><li>Бюллетени</li><li>Идеи</li></ul>|
|Реагирование на инцидент| `com.microsoft.teams.template.CoordinateIncidentResponse`|Каналы: <ul><li>Общие<li>Объявления</li><li>Логистика</li><li>Планирование</li><li>Восстановления</li><li>Срочно</li></ul> Приложения: <ul><li>Вики</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Задачи</li> <li>Утверждения</li> <li>Проверка</li> <li>Power Automate</li><li>Бюллетени</li><li>Вехи</li></ul>|
|Больница| `com.microsoft.teams.template.healthcareHospital` |Каналы: <ul><li>Общие</li><li>Объявления</li><li>Соответствие требованиям</li><li>Госпитализация</li><li>Кадры</li><li>Аптека</li></ul> Приложения: <ul><li>Вики</li><li>Списки</li><li>Задачи</li><li>Утверждения</li><li>Смены</li><li>Бюллетени</li><li>Проверка</li><li>Идеи</li></ul>|
|Организация магазина| `com.microsoft.teams.template.retailStore` |Каналы: <ul><li>Общие<li>Передача смены</li><li>Готовность магазина</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li><li>Смены</li><li>Проверка</li></ul>|
|Розница для руководителей| `com.microsoft.teams.template.retailManagerCollaboration` |Каналы: <ul><li>Общие<li>Операции</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li><li>Проверка</li></ul>|
|Качество и безопасность |`com.microsoft.teams.template.QualitySafety`|Каналы: <ul><li>Общие<li>Объявления</li><li>Руководство</li><li>Обслуживания</li><li>Production Line 1</li><li>Production Line 2</li><li>Production Line 3</li><li>Здоровье и безопасность</li><li>Учебный курс</li><li>Развлечения</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li> <li>Сообщающий о проблеме</li> <li>Проверка</li> </ul>|
|Управление волонтерами| `com.microsoft.teams.template.ManageVolunteers` |Каналы: <ul><li>Общие<li>Объявления</li><li>Отчётность</li><li>Управление волонтерами</li><li>Возможности взаимодействия</li><li>Подключение волонтеров</li></ul> Приложения: <ul><li>Веб-сайт</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Задачи</li><li>SharePoint</li><li>OneNote</li></ul>|
||||

### <a name="team-templates-by-category-and-industry"></a>Шаблоны команд по категориям и от отрасли

Дополнительные сведения о том, как использовать встроенные шаблоны в вашей отрасли, см. в:

- [Шаблоны финансовой группы](financial-teams-templates-in-the-admin-console.md)
- [Общие шаблоны команд](general-teams-templates-in-the-admin-console.md)
- [Шаблоны для государственных команд](government-teams-templates-in-the-admin-console.md)
- [Шаблоны медицинских команд](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Шаблоны производственных команд](manufacturing-teams-templates-in-the-admin-console.md)
- [Шаблоны некоммерческих команд](team-templates-nonprofit.md)
- [Шаблоны розничных команд](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>Ограничения размера шаблона группы

Шаблоны ограничиваются определенным количеством каналов, вкладок и приложений.

 > [!Note]
 > После создания шаблона в команду можно добавить дополнительные каналы, вкладки и приложения.

|Функция | Предел|
|-|-|
|Каналы для каждого шаблона | 15 |
|Вкладки для каждого канала в шаблоне | 20 |
|Приложения для каждого шаблона | 50|
|||

Дополнительные сведения см. [в этой](limits-specifications-teams.md) Teams.

## <a name="manage-team-templates"></a>Управление шаблонами команд

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Управление шаблонами команд в Центре администрирования Teams

#### <a name="view-team-templates"></a>Просмотр шаблонов команд

Чтобы просмотреть шаблоны групп, в левой области навигации центра администрирования Teams перейдите к шаблонам **Teams** >  **Team**. Выберите шаблон, чтобы увидеть дополнительные сведения, включая каналы и приложения, которые он содержит.

#### <a name="create-your-own-team-templates"></a>Создание собственных шаблонов команд

Вы можете создавать собственные настраиваемые шаблоны с нуля, из существующей команды и из существующего шаблона. Дополнительные сведения см. в статьях

- [Создание пользовательского шаблона команды](create-a-team-template.md)
- [Создание шаблона из существующей команды](create-template-from-existing-team.md)
- [Создание шаблона команды из существующего шаблона группы](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Применение политик шаблонов команд

Чтобы управлять шаблонами, которые пользователи видят в Teams для создания [команд, можно](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) настроить политики шаблонов и назначить их пользователям и группам в организации. Дополнительные узнать об этом см. в [Teams центре администрирования](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Управление шаблонами команд с помощью PowerShell

Для управления шаблонами в PowerShell используйте следующие cmdlets:

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>Статьи по теме

- [Создание команды на основе шаблона](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Начало работы с шаблонами команд с помощью Microsoft Graph](get-started-with-teams-templates.md)
- [Клонирование команды](/graph/api/team-clone?view=graph-rest-1.0&tabs=http)
