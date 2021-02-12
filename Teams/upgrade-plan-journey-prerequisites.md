---
title: Предварительные условия и зависимости среды для перехода на Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Используйте это руководство, чтобы узнать о предварительных и зависимостей среды для развертывания Teams в организации.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578282"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Необходимые условия и зависимости от среды для Teams

![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")

Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователя. Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:

- [Привлечение заинтересованных лиц проекта](upgrade-enlist-stakeholders.md)
- [Определение области проекта](https://aka.ms/SkypetoTeams-Scope)
- [Понимание сосуществования и совместной работы Skype для бизнеса и Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Выбранный путь обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams объединяет несколько служб Microsoft 365 и Office 365 и поэтому зависит от правильной реализации и работы этих служб. К таким службам относятся SharePoint Online, Exchange Online и OneDrive для бизнеса, но не ограничивайтесь ими.

Хотя не все службы требуются, настоятельно рекомендуем внедрить все из них. Если вы решите не внедрять определенные службы, это повлияет на функции, которые Teams может предложить вашей организации. Например, хотя вам и не нужно внедрять SharePoint Online, в Teams есть определенные функции SharePoint Online, такие как обмен файлами в групповых беседах, поэтому реализация этой службы снизит функциональность клиента.

В следующих статьях вы узнаете о предварительных условиях и взаимодействии Teams с другими технологиями.

- Если ваша организация не развернула рабочие нагрузки Microsoft 365 или [](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)Office 365, см.

- Если ваша организация не добавила или не настроил проверенный домен для Microsoft 365 или Office 365, см. вопрос и вопрос о [доменах.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Если ваша организация не синхронизировала удостоверения с Azure Active Directory, см. модели удостоверений и проверку подлинности [в Microsoft Teams.](identify-models-authentication.md)

- Если в вашей организации нет Exchange Online, узнайте, как [exchange и Microsoft Teams взаимодействуют.](Exchange-Teams-interact.md)

- Если в вашей организации нет SharePoint Online, узнайте, как SharePoint Online и OneDrive для бизнеса взаимодействуют [с Microsoft Teams.](SharePoint-OneDrive-interact.md)

- Чтобы узнать, как [взаимодействуют группы Microsoft 365 и Microsoft Teams.](Office-365-groups.md)

- Если ваша организация является учебным заведением и вы используете систему сведений об учащихся, см. статью "Добро пожаловать в [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) перед развертыванием Microsoft Teams".

- Если в вашей организации рассматриваются варианты звонков по телефонной сети общего звонков (МСК), см. параметры "Голосовая связь [—](cloud-voice-landing-page.md)телефонная система" и "Подключение к СТАНП", [](calling-plan-landing-page.md)"Какой план звонков вам подошел" и "Прямая маршрутия телефонной системы". [](direct-routing-landing-page.md)

- Чтобы убедиться в том, что все требования к сети выполнены перед развертыванием Teams, см. команду "Подготовка сети организации [к развертыванию Microsoft Teams".](prepare-network.md)

Убедився, что ваша среда соответствует всем необходимым требованиям, оцените текущую [среду для Teams.](upgrade-plan-journey-evaluate-environment.md)
