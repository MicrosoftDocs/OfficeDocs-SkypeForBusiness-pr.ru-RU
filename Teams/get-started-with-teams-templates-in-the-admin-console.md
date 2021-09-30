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
description: Узнайте о шаблонах групп и управлении ими в центре Microsoft Teams администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30d2ef7baf485e617ac5d703659a79d6f57e7f76
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011783"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Начало работы с шаблонами команд в Центре администрирования Teams

**Возможность создавать пользовательские шаблоны пока не поддерживается пользователями EDU.**

> [!NOTE]
> Частные каналы и метки конфиденциальности в настоящее время не поддерживаются в шаблонах группы. Создание частного канала не включается в определения шаблонов. Параметр метки конфиденциальности в **потоке** создания команды из шаблона не применяется к команде.

## <a name="overview"></a>Обзор

Шаблон группы в Microsoft Teams — это определение структуры группы, разработанной на реализации бизнес-потребности или проекта. Как администратор вы можете использовать шаблоны для простого развертывания согласованных групп в организации. С помощью шаблонов пользователи могут быстро создавать форматирование пространства для совместной работы с заранее задав параметры, каналы и приложения.

Вы можете управлять шаблонами групп в Microsoft Teams центре администрирования или с помощью PowerShell. Вы можете использовать встроенные шаблоны, которые мы предоставляем, а также создавать [собственные.](#create-your-own-team-templates) Вы также [можете применять политики шаблонов](#apply-team-template-policies) для управления тем, какие шаблоны доступны пользователям в Teams.

В этой статье представлен обзор работы с шаблонами групп в Центре Teams администрирования. Вы узнаете о свойствах, которые поддерживаются в шаблонах, готовых шаблонах, ограничениях на размер шаблонов, о том, как создавать шаблоны и управлять ими, а также делать много другое.

> [!NOTE]
> Пользователи могут [создавать команды из встроенных](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) или настраиваемых шаблонов в Teams приложения. Разработчики также могут программным путем создавать команды из встроенных шаблонов команд с помощью Microsoft Graph. Подробнее см. в этой ссылке. Начало работы с шаблонами команд [с помощью Microsoft Graph.](get-started-with-teams-templates.md)

## <a name="team-template-capabilities"></a>Возможности шаблонов команд

Большинство свойств группы включаются и поддерживаются шаблонами команд. Но есть несколько свойств и функций, которые в настоящее время не поддерживаются. Вот краткое описание того, что входит в шаблоны команд.

| **Свойства группы, поддерживаемые шаблонами команд** | **Свойства группы пока не поддерживаются шаблонами команд** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Тип шаблона | Участники команды |
| Название команды | Изображение группы |
| Описание группы | Параметры канала |
| Видимость группы (общедоступный или закрытый) | Соединители |
| Параметры команды (например, упоминания участника, гостя и @) | Файлы и контент |
| Канал autofavorite | |
| Установленное приложение | |
| Закрепленные вкладки | |

> [!NOTE]
> Мы добавим дополнительные возможности шаблонов в будущих выпусках Microsoft Teams, поэтому ознакомьтесь с самой информацией о поддерживаемых свойствах.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Встроенные шаблоны групп в Центре Teams администрирования

Вот готовые шаблоны команд, которые можно найти в Teams администрирования. Готовые шаблоны — это шаблоны, созданные для определенных отраслей. Чтобы просмотреть эти шаблоны, в левой области навигации центра администрирования Teams перейдите в Teams  >  **шаблоны групп**.

Вы можете дублировать встроенные шаблоны, но не редактировать их. Если вы хотите изменить свойства встроенного шаблона, можно создать новый шаблон из существующего, а затем добавить или удалить нужные свойства. Помните, что некоторые свойства некоторых шаблонов изменить нельзя.

| Тип шаблона | TemplateId | Свойства этого шаблона |
| ------------------ | -------------- | ----------------------------------------------------- |
| Принять Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Угловой угол химок</li> <li>Формы команд</li><li>Календарь</li></ul> Приложения: <ul><li>Вики</li>  <li>Календарь канала</li> <li>Вехи</li><li>Бюллетени</li></ul>|
| Управление проектом |`com.microsoft.teams.template.ManageAProject`| Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Ресурсы</li> <li>Планирование</li></ul> Приложения:<ul><li>Вики</li><li>OneNote</li><li>Задачи</li><li>Списки</li><li>Power Automate</li></ul> |
| Управление событием|`com.microsoft.teams.template.ManageAnEvent` | Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Бюджет</li> <li>Содержимое</li><li>Логистика</li> <li>Планирование</li> <li> Маркетинг и PR</li></ul> Приложения:<ul><li>Вики</li><li>Сайт</li> <li>YouTube</li> <li>Задачи</li> <li>OneNote</li> <li>Идеи сотрудников</li> <li>Issue Reporter</li><li>Power Automate</li><li>Бюллетени</li><li>Вехи</li></ul> |
|Сотрудники, работающие на доске|`com.microsoft.teams.template.OnboardEmployees` | Каналы: <ul><li>Общие</li> <li>Объявления</li> <li>Чат сотрудника</li> <li>Обучение</li></ul>Приложения:<ul><li>Вики</li><li>Общин</li><li>Задачи</li><li>Идеи сотрудников</li><li>Power Automate</li><li>Бюллетени</li><li>Вехи</li></ul>|
|Организовать службу поддержки| `com.microsoft.teams.template.OrganizeHelpDesk`|Каналы:<ul><li>Общие</li><li>Объявления</li><li>Вопросы и ответы</li></ul>Приложения:<ul><li>Вики</li><li>OneNote</li><li>Задачи </li><li>Благодарность</li><li>Issue Reporter</li><li>Power Automate</li><li>Бюллетени</li></ul> |
| Уход за пациентом| `com.microsoft.teams.template.healthcareWard`| Каналы:<ul><li>Общие</li><li>Объявления</li><li>Совещания</li><li>Обходы</li><li>Персонал</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Списки  </li><li>Утверждения</li><li>Бюллетени</li><li>Проверка</li></ul>|
| Связь скризис |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Каналы: <ul><li>Общие<li>Объявления</li><li>Новости мира</li><li>Внутренние запятые</li><li>Внешние запятые</li><li>Запрос на утверждение</li><li>Рост клиентов</li><li>Обновление руководства</li><li>Планирование</li><li>Логистика</li></ul>Приложения: <ul><li>Сайт</li><li>Задачи</li><li>Issue Reporter</li><li>Утверждения</li><li>Бюллетени</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|Bank branch| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Каналы: <ul><li>Общие<li>Объявления</li><li>Совещания</li><li>Собрания клиентов</li><li>Запрос на утверждение </li><li>Коучинг</li><li>Разработка навыков</li><li>Обработка ссуды</li><li>Жалобы клиентов</li><li>Слава</li><li>Интересные материалы</li><li>Соответствие требованиям</li></ul>Приложения:<ul><li>Благодарность </li><li>Issue Reporter</li><li>Вики</li><li>Календарь</li><li>Утверждения</li><li>Бюллетени</li><li>Идеи</li></ul>|
|Реагирование на инцидент| `com.microsoft.teams.template.CoordinateIncidentResponse`|Каналы: <ul><li>Общие<li>Объявления</li><li>Логистика</li><li>Планирование</li><li>Восстановления</li><li>Срочно</li></ul> Приложения: <ul><li>Вики</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Задачи</li> <li>Утверждения</li> <li>Проверка</li> <li>Power Automate</li><li>Бюллетени</li><li>Вехи</li></ul>|
|Больница| `com.microsoft.teams.template.healthcareHospital` |Каналы: <ul><li>Общие</li><li>Объявления</li><li>Соответствие требованиям</li><li>Госпитализация</li><li>Кадры</li><li>Аптека</li></ul> Приложения: <ul><li>Вики</li><li>Списки</li><li>Задачи</li><li>Утверждения</li><li>Смены</li><li>Бюллетени</li><li>Проверка</li><li>Идеи</li></ul>|
|Организация магазина| `com.microsoft.teams.template.retailStore` |Каналы: <ul><li>Общий<li>Передача смены</li><li>Готовность магазина</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li><li>Смены</li><li>Проверка</li></ul>|
|Розница для руководителей| `com.microsoft.teams.template.retailManagerCollaboration` |Каналы: <ul><li>Общий<li>Операции</li><li>Обучение</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li><li>Проверка</li></ul>|
|Качество и безопасность |`com.microsoft.teams.template.QualitySafety`|Каналы: <ul><li>Общие<li>Объявления</li><li>Руководство</li><li>Обслуживания</li><li>Production Line 1</li><li>Production Line 2</li><li>Production Line 3</li><li>Здоровье и безопасность</li><li>Обучение</li><li>Интересные материалы</li></ul> Приложения: <ul><li>Вики</li><li>Задачи</li> <li>Issue Reporter</li> <li>Проверка</li> </ul>|

### <a name="team-templates-by-category-and-industry"></a>Шаблоны команд по категориям и от отрасли

Дополнительные сведения о способах использования встроенных шаблонов в отрасли см. в:

- [Шаблоны финансовой группы](financial-teams-templates-in-the-admin-console.md)
- [Общие шаблоны команд](general-teams-templates-in-the-admin-console.md)
- [Шаблоны для государственных команд](government-teams-templates-in-the-admin-console.md)
- [Шаблоны медицинских команд](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Шаблоны производственных команд](manufacturing-teams-templates-in-the-admin-console.md)
- [Шаблоны розничных команд](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>Ограничения размера шаблона группы

Шаблоны ограничиваются определенным количеством каналов, вкладок и приложений.

 > [!Note]
 > После создания шаблона в команду можно добавить дополнительные каналы, вкладки и приложения.

|Компонент | Предел|
|-|-|
|Каналы для каждого шаблона | 15 |
|Вкладки для каждого канала в шаблоне | 20 |
|Приложения для каждого шаблона | 50|
|||

Дополнительные сведения см. [в этой](limits-specifications-teams.md)Teams.

## <a name="manage-team-templates"></a>Управление шаблонами команд

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Управление шаблонами команд в Центре администрирования Teams

#### <a name="view-team-templates"></a>Просмотр шаблонов команд

Чтобы просмотреть шаблоны групп, в левой области навигации центра администрирования Teams перейдите в Teams  >  **шаблоны групп**. Выберите шаблон, чтобы увидеть дополнительные сведения, включая каналы и приложения, которые он содержит.

#### <a name="create-your-own-team-templates"></a>Создание собственных шаблонов команд

Вы можете создавать собственные настраиваемые шаблоны с нуля, из существующей команды и из существующего шаблона. Дополнительные сведения см. в статьях

- [Создание пользовательского шаблона команды](create-a-team-template.md)
- [Создание шаблона из существующей команды](create-template-from-existing-team.md)
- [Создание шаблона команды из существующего шаблона группы](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Применение политик шаблонов команд

Чтобы управлять шаблонами, которые пользователи видят в Teams для создания команд, можно настроить политики шаблонов и назначить их пользователям и группам в организации. Дополнительные информации см. в центре администрирования [Teams управление шаблонами групп.](templates-policies.md)

### <a name="manage-team-templates-using-powershell"></a>Управление шаблонами команд с помощью PowerShell

Для управления шаблонами в PowerShell используйте следующие cmdlets:

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>Статьи по теме

- [Создание команды на 2016 г. на 2016 г.](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [Начало работы с шаблонами команд с помощью Microsoft Graph](get-started-with-teams-templates.md) 