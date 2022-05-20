---
title: "\"Смены\" для Teams"
description: Получите рекомендации администратора, необходимые для настройки и управления сменами, средством управления расписанием, в Teams.
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
ms.openlocfilehash: f8980116dab90abd3c9c96ac17b577e6abf64f90
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598312"
---
# <a name="shifts-for-teams"></a>"Смены" для Teams

Shifts, средство управления расписанием в Teams, обеспечивает подключение и синхронизацию сотрудников переднего плана. Он сначала создает мобильные устройства для быстрого и эффективного управления расписанием и обмена данными. С помощью смен руководители и сотрудники могут легко управлять расписаниями и поддерживать связь.

Руководители могут создавать, обновлять и управлять расписаниями смен для своих команд. Они могут назначать смены, добавлять открытые смены и утверждать запросы на расписание от сотрудников. Сотрудники могут просматривать собственные и командные расписания, задавать их доступность, запрашивать смену или предложение смены, запрашивать время ожидания, а также время ожидания и выход.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Используйте следующие ресурсы, чтобы настроить смены в организации и управлять ими.

## <a name="set-up-and-manage-shifts"></a>Настройка смен и управление ими

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Управление сменами](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Узнайте, как управлять сменами в организации.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Управление владельцами расписания для управления сменами](shifts/schedule-owner-for-shift-management.md)** Эта функция позволяет повысить разрешения члена команды до владельца расписания, не делая сотрудника владельцем команды.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Часто задаваемые вопросы о сменах данных](shifts/shifts-data-faq.md)** Узнайте, где хранятся данные shifts и другие разделы, связанные с данными shifts, включая хранение, извлечение и шифрование.        |

## <a name="shifts-connectors"></a>Соединители shifts

Если для планирования используется система управления персоналом сторонних разработчиков (WFM), вы можете напрямую интегрироваться со сменами с помощью управляемых соединителей shifts. После настройки подключения сотрудники переднего плана могут без проблем просматривать свои расписания в системе WFM и управлять ими в shifts.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Общие сведения о соединителях shifts](shifts/shifts-connectors.md)** Ознакомьтесь с общими сведениями о соединителях Shifts и их работе. Узнайте о доступных управляемых соединителях и поддерживаемых системах WFM.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Соединители управляемых смен](shifts/shifts-connectors.md#managed-shifts-connectors)** Соединители Managed Shifts, разработанные совместно с нашими партнерами, размещаются и управляются либо нами, либо нашими партнерами. Дополнительные сведения см. [в статье Microsoft Teams Shifts connector for Blue Yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) and [Excelis Shifts connector for Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Использование мастера соединителя Shifts для подключения shifts к Blue Yonder Workforce Management](shifts/shifts-connector-wizard.md)** Мастер соединителя shifts в Центр администрирования Microsoft 365 помогает быстро настроить подключение к системе WFM. В настоящее время мастер поддерживает соединитель Teams Shifts для Blue Yonder для интеграции Shifts с Blue Yonder Workforce Management.
|  | **[Подключение shifts к Blue Yonder Workforce Management с помощью PowerShell](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Узнайте, как с помощью PowerShell настроить подключение к Blue Yonder Workforce Management с помощью соединителя Teams Shifts для Blue Yonder.         |
|   | **[Управление подключением Shifts к Blue Yonder Workforce Management с помощью PowerShell](shifts/shifts-connector-powershell-manage.md)** Получите рекомендации по использованию PowerShell для управления подключением Shifts к Blue Yonder Workforce Management после настройки с помощью мастера соединителя Shifts или PowerShell.

## <a name="shifts-extensions"></a>Сдвиги расширений

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** shifts Graph API позволяют интегрировать данные Shifts с системами управления внешними сотрудниками (WFM). Вы сможете создавать пользовательские функции shifts в серверной части, предоставляя пользователям широкие возможности внешнего интерфейса в Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** shifts + Power Automate позволяет принимать информацию из shifts и создавать настраиваемые рабочие процессы с другими приложениями и выполнять операции в большом масштабе. Автоматизировать ключевые процессы практически без кода. Триггеры и шаблоны поддерживают различные сценарии, такие как включение автоматического утверждения для запросов на смену, когда утверждение руководителя не требуется. |

## <a name="featured-training"></a>Тематическое обучение

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Видео: что такое смены?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Видео: создание расписания смен](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Видео: управление расписанием смен](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
