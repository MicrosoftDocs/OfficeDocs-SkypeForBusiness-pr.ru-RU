---
title: Необходимые условия и зависимости от среды для перехода на Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Воспользуйтесь этим руководством, чтобы узнать о предварительных и зависимостей среды для Teams организации.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f10df8849e6efe4e6ceac38cb46d118dff5a8ff8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725458"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Предварительные условия и зависимости от среды для Teams

![Схема пути обновления с акцентом на этапе технической готовности.](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")

Эта статья является частью этапа технической готовности, которое вы завершаете параллельно со этапом подготовки пользователей. Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:

- [Привлечение заинтересованных лиц по проекту](upgrade-enlist-stakeholders.md)
- [Определение области проекта](./upgrade-define-project-scope.md)
- [Понятное сосуществование и совместное Skype для бизнеса и Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Выбор пути обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams объединяют несколько Microsoft 365 и Office 365 служб, поэтому они зависят от правильной реализации и работы этих служб. Эти службы включают (но не ограничиваются) службами SharePoint Online, Exchange Online и OneDrive для бизнеса.

Хотя не все службы требуются, настоятельно рекомендуем внедрить все из них. Если вы решите не внедрять определенные службы, это повлияет на функции, которые Teams предложить вашей организации. Например, если вам не нужно внедрять SharePoint Online, Teams в SharePoint Online есть определенные функции, такие как общий доступ к файлам в групповых беседах, поэтому не внедрение этой службы уменьшит функциональные возможности, предлагаемые клиентом.

В следующих статьях вы узнаете о необходимых предварительных Teams взаимодействия с другими технологиями.

- Если ваша организация не развернула рабочие нагрузки Microsoft 365 или Office 365, см. начало [работы.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Если ваша организация не добавила или не настроил проверенный домен для Microsoft 365 или Office 365, см. вопрос [и о доменах.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Если ваша организация не синхронизировала удостоверения с Azure Active Directory, см. в [Microsoft Teams.](identify-models-authentication.md)

- Если в вашей организации нет Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](Exchange-Teams-interact.md).

- Если в вашей организации нет SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](SharePoint-OneDrive-interact.md).

- Чтобы узнать, [как Microsoft 365 группы и Microsoft Teams взаимодействие.](Office-365-groups.md)

- Если ваша организация является учебным заведением и вы используете систему сведений об учащихся, см. статью Добро пожаловать в [Microsoft Синхронизация сведений о школе](/schooldatasync) перед развертыванием Microsoft Teams.

- Если в вашей организации рассматриваются варианты звонков по телефонной сети общего звонков (STN), см. параметры Голосовая связь [— телефонная система](cloud-voice-landing-page.md)и Подключение по ЗВОНКОВ [,](calling-plan-landing-page.md)Какой план звонков вам больше всего подошел, и [телефонная система](direct-routing-landing-page.md)прямой маршрутизации.

- Чтобы убедиться, что все требования к сети выполнены до Teams, см. в [Microsoft Teams.](prepare-network.md)

- Если вы используете Skype для бизнеса Online Connector для управления службами, необходимо перейти в модуль Teams PowerShell и обновить существующие сценарии PowerShell. Дополнительные сведения см. в Skype для бизнеса Online Connector в [модуле Teams PowerShell.](teams-powershell-move-from-sfbo.md)

Убедився, что ваша среда соответствует всем необходимым требованиям, оцените текущую среду [для Teams.](upgrade-plan-journey-evaluate-environment.md)