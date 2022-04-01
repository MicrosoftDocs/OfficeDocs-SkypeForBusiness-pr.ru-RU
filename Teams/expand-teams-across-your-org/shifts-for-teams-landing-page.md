---
title: "\"Смены\" для Teams"
description: Получите рекомендации администратора, необходимые для создания и управления сменами , средством управления расписанием, в Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592775"
---
# <a name="shifts-for-teams"></a>"Смены" для Teams

Смены, средство управления расписанием в Teams, обеспечивает подключение и синхронизацию сотрудников. Оно сначала встроено на мобильных устройствах для быстрого и эффективного управления расписаниями и связи. С помощью shifts руководители и работники могут легко управлять расписаниями и поддерживать связь.

Руководители могут создавать, обновлять расписания смен и управлять ими в своих командах. Они могут назначать смены, добавлять открытые смены и утверждать запросы на расписание от сотрудников. Сотрудники могут просматривать собственные расписания и расписания своей группы, устанавливать их доступность, запрашивать обмен сменами или предлагать смены, запрашивать отключки, а также часы в и на работе.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Воспользуйтесь следующими ресурсами, чтобы настроить смены в организации и управлять ими.

## <a name="set-up-and-manage-shifts"></a>Настройка смен и управление ими

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Управление сменами](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Узнайте, как управлять сменами в организации.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Управление владельцами расписания для управления сменами](shifts/schedule-owner-for-shift-management.md)** Эта функция позволяет повысить разрешения участника группы до владельца расписания, не назначить сотрудника владельцем команды.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Смены данных: faq](shifts/shifts-data-faq.md)** Узнайте, где хранятся данные Shifts, и другие разделы, связанные с данными Shifts, включая хранение, и извлечь данные и шифрование.        |

## <a name="shifts-connectors"></a>Соединитетели смен

Если вы используете для планирования систему управления трудовыми ресурсами сторонних компаний, вы можете интегрироваться непосредственно со сменами через управляемые соединители смен, а также через API и SDK для shifts Graph Shifts с открытым кодом. После того как вы настроите подключение, сотрудники, работающие с телефоном, смогут без проблем просматривать свои расписания в WFM-системе и управлять ими в сменах.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Общие сведения о соединителах смен](shifts/shifts-connectors.md)** Общие сведения о соединителах Смены и их работе. Узнайте о доступных соединителах с управляемыми данными и с открытым кодом, а также о поддерживаемых системах WFM.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Соединители управляемых смен](shifts/shifts-connectors.md#managed-shifts-connectors)** Соединители Управляемые смены, разработанные в совместной работе с нашими партнерами, находятся и управляются нами или нашими партнерами. Дополнительные информации см. [](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) в Microsoft Teams соединителя "Синий висяк" и ["Реакторов" для Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Использование мастера соединителя "Смены" для подключения shifts к управлению ресурсами "Синий Yonder"](shifts/shifts-connector-wizard.md)** Мастер соединители "Смены" в Центр администрирования Microsoft 365 позволяет быстро настроить подключение к системе WFM. В настоящее время мастер поддерживает соединителя Teams Смены для синего желтодера, чтобы интегрировать смены с управлением персоналом "Синий Yonder".
|  | **[Использование PowerShell для подключения shifts к управлению ресурсами "синий Yonder"](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Узнайте, как с помощью PowerShell настроить подключение к управлению ресурсами Teams Blue Yonder.         |
|   | **[Использование PowerShell для управления подключением к сменам для управления ресурсами "Синий Yonder"](shifts/shifts-connector-powershell-manage.md)** Получите инструкции по использованию PowerShell для управления подключением "Смены" к управлению рабочими ресурсами "Синий Yonder", после того как вы настроите его с помощью мастера соединителя Shifts или PowerShell.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[Соединители Смены с открытым кодом](/microsoftteams/platform/samples/shifts-wfm-connectors)** Узнайте, как использовать [](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) соединителы с открытым кодом на основе сообщества для интеграции системы Kronos или JDA WFM с помощью API и SDK с помощью Graph Shifts.    |

## <a name="shifts-extensions"></a>Расширения смен

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** Shifts Graph API позволяют интегрировать данные Shifts с системами управления внешними ресурсами (WFM). Вы сможете создавать пользовательские смены в задней части, предоставляя пользователям гибкий и передний Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[С помощью shifts+ Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** shifts + Power Automate вы можете взять информацию из shifts и создать пользовательские рабочие процессы с другими приложениями и выполнять масштабные операции. Автоматизировать ключевые процессы практически без кода. Триггеры и шаблоны поддерживают различные сценарии, например включение автоматического утверждения запросов на смену, если утверждение руководителя не требуется. |

## <a name="featured-training"></a>Тематическое обучение

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Видео. Что такое смены?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Видео: создание расписания смен](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Видео: управление расписанием смен](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
