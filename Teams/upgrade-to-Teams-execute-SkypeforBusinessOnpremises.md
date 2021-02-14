---
title: Переход с локальной среды Skype для бизнеса на Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как перейти с локального развертывания Skype для бизнеса на Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820949"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Обновление локального развертывания Skype для бизнеса до Teams

![Этапы пути обновления с акцентом на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")

Эта статья является частью этапа развертывания и реализации, которое вы начинаете. Прежде чем продолжается, подтвердим, что вы выполнили следующие действия:

- [Привлечение заинтересованных лиц проекта](upgrade-enlist-stakeholders.md)
- [Определение области проекта](https://aka.ms/SkypetoTeams-Scope)
- [Понимание сосуществования и совместной работы Skype для бизнеса и Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Выбранный путь обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовлена среда](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Подготовив организацию](https://aka.ms/SkypeToTeams-UserReadiness)
- [Проводится пилотный проект](https://aka.ms/SkypeToTeams-Pilot)

Следуйте указаниям в этой статье, если вы развернули локальное приложение Skype для бизнеса или Microsoft Lync и хотите выборочно перейти на Microsoft Teams с помощью нескольких режимов сосуществования или в режиме all-in. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Шаг 1. Развертывание гибридного подключения

Для обновления пользователей до Teams необходимо развернуть гибридное подключение.

Дополнительные сведения см. в [сведениях о развертывании](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online.

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Шаг 2. Реализация выбранного пути обновления для организации

После завершения гибридной настройки вы можете запланировать перемещение пользователей на Microsoft 365 или Office 365.

Дополнительные сведения см. в:

- [TeamsUpgradePolicy: управление миграцией и сосуществованием.](upgrade-to-teams-on-prem-tools.md)

- [Перемещение пользователей из локальной сети в Skype для бизнеса Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и Teams

Переход с локальной телефонной системы на Teams позволит вам воспользоваться прямой маршрутией телефонной системы ("Прямая маршрутия") или предоставленными Майкрософт планами звонков для Microsoft 365 или Office 365.

Если вы не используете планы звонков, необходимо перейти с корпоративного развертывания голосовой связи на прямую маршрутизаку телефонной системы в рамках обновления до Teams.

Дополнительные сведения см. [в дополнительных сведениях о прямой маршрутике телефонной системы.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing) Если вы планируете использовать планы звонков, обратитесь к нашим рекомендациям по переносу номеров [телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)