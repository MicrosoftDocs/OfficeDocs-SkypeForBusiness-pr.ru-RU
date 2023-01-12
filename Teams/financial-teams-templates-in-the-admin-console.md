---
title: Использование шаблонов финансовых команд
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Сведения о том, как управлять шаблонами финансовых команд и использовать их в Центре администрирования Teams и в Microsoft Graph для быстрого и простого создания команд в организации по оказанию финансовых услуг.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea67bec0fd8750e32ebb5f65d0258fa7c172a46
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778949"
---
# <a name="use-financial-team-templates"></a>Использование шаблонов финансовых команд

С помощью шаблонов команд в Microsoft Teams можно быстро и легко создавать команды с готовой командной структурой параметров, каналов и предустановленных приложений.

В организациях, оказывающих финансовые услуги, шаблоны команд могут быть особенно полезны, так как помогают быстро формировать единообразные команды по всей организации. Шаблоны также помогают сотрудникам понять, как эффективно использовать Teams.

В состав Teams входят шаблоны, специально разработанные для организаций по оказанию финансовых услуг. Эти готовые шаблоны можно использовать с целью быстрого создания команд для общения и взаимодействия сотрудников. В этой статье вы познакомитесь с каждым шаблоном и рекомендуемыми способами их использования.

Способ использования шаблонов команд и управления ими зависит от того, являетесь ли вы администратором или разработчиком.

|Если вы: | Вы можете: |
| ---- | --------- |
| Администратор или ИТ-специалист |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Разработчик | [Использовать Microsoft Graph](#use-team-templates-with-microsoft-graph) для создания команд из шаблонов. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Управление шаблонами команд в Центре администрирования Teams

Как администратор вы можете управлять шаблонами команд в Центре администрирования Microsoft Teams. Здесь можно просмотреть подробные сведения о каждом шаблоне. Вы также можете [создавать и назначать политики шаблонов](templates-policies.md) сотрудникам, чтобы управлять тем, какие шаблоны они видят в Teams [для создания команд](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами команд в Центре администрирования Teams](get-started-with-teams-templates-in-the-admin-console.md).

Сейчас мы предлагаем следующие готовые шаблоны команд для организаций по оказанию финансовых услуг. Чтобы просмотреть их, в левой области навигации Центра администрирования Teams выберите **Teams** > **Шаблоны команд**.

### <a name="bank-branch"></a>Банковский филиал

Централизация совместной работы сотрудников банковского филиала для проведения совещаний, встреч с клиентами, выполнения бизнес-процессов, таких как сотрудничество при оформлении ипотеки, а также массового информирования сотрудников (объявления, поздравления).

>[!div class="mx-tdBreakAll"]
>| Тип шаблона |TemplateId| Свойства этого шаблона |
>| ------------------ |--|----------------------------------------------------- |
>|Банковский филиал| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Каналы: <ul><li>Общий<li>Объявления</li><li>Совещания</li><li>Собрания клиентов</li><li>Запрос на утверждение </li><li>Обучение</li><li>Развитие навыков</li><li>Обработка кредита</li><li>Жалобы клиентов</li><li>Поздравления</li><li>Забавные вещи</li><li>Соответствие требованиям</li></ul>Приложения:<ul><li>Утверждения</li><li>Бюллетени</li><li>Календарь канала</li><li>Идеи сотрудников</li><li>Отчеты о проблемах</li><li>Благодарность</li><li>Смены</li><li>Вики</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Использование шаблонов команд с помощью Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>Банковский филиал

Централизация совместной работы сотрудников банковского филиала для проведения совещаний, встреч с клиентами, выполнения бизнес-процессов, таких как сотрудничество при оформлении ипотеки, а также массового информирования сотрудников (объявления, поздравления).

>[!div class="mx-tdBreakAll"]
>| Тип шаблона |TemplateId| Каналы шаблона |
>| ------------------ |--|----------------------------------------------------- |
>|Банковский филиал|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Общий<br>Объявления<br>Совещания<br>Собрания клиентов<br>Запрос на утверждение<br>Обучение<br>Развитие навыков<br>Обработка кредита<br>Жалобы клиентов<br>Поздравления<br>Забавные вещи<br>Соответствие требованиям|

> [!NOTE]
> Дополнительные шаблоны команд, применимые к организациям по оказанию финансовых услуг, см. в статье [Встроенные в Microsoft Graph шаблоны команд для малого и среднего бизнеса](smb-templates.md).

## <a name="related-articles"></a>Статьи по теме

- [Начало работы с шаблонами команд в Центре администрирования Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Создание команды на основе шаблона](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Начало работы с шаблонами команд с помощью Microsoft Graph](get-started-with-teams-templates.md)