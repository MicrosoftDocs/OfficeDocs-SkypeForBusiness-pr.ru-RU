---
title: Переход с локальной среды Skype для бизнеса на Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как перейти на Microsoft Teams из локального Skype для бизнеса организации.
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
ms.openlocfilehash: 1bf5529cf37ca3217c5af0411a1d12f0e752c583cb869273f9ba5b068d5633da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298999"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Обновление с локального Skype для бизнеса до Teams

![Этапы пути обновления с акцентом на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")

Эта статья является частью этапа развертывания и реализации, на который вы входите. Прежде чем при этом подтверждать, что вы выполнили следующие действия:

- [Привлечение заинтересованных лиц по проекту](upgrade-enlist-stakeholders.md)
- [Определение области проекта](./upgrade-define-project-scope.md)
- [Понятное сосуществование и совместное Skype для бизнеса и Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Выбор пути обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовить среду](./upgrade-prepare-environment.md)
- [Подготовленные организации](./upgrade-prepare-organization.md)
- [Пилотный проект](./pilot-essentials.md)

Следуйте указаниям из этой статьи, если вы развернули локальное развертывание Skype для бизнеса или Microsoft Lync и хотите перейти на Microsoft Teams выборочно — с помощью нескольких режимов совместной работы или всех. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Шаг 1. Развертывание гибридного подключения

Для обновления пользователей до Teams необходимо развернуть гибридное подключение.

Дополнительные сведения см. в [теме Развертывание гибридного](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) подключения между Skype для бизнеса Server и Skype для бизнеса Online.

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Шаг 2. Реализация выбранного пути обновления для организации

После завершения гибридной настройки вы можете запланировать перемещение пользователей на Microsoft 365 или Office 365.

Дополнительные сведения см. в:

- [TeamsUpgradePolicy: управление миграцией и сосуществованием.](upgrade-to-teams-on-prem-tools.md)

- [Перемещение пользователей из локальной сети в Skype для бизнеса Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>телефонная система и Teams обновления

Переход с локальной телефонной системы на Teams позволит вам воспользоваться преимуществами прямой маршрутации телефонная система ("Прямая маршрутия") или планов звонков, предоставленных Майкрософт для Microsoft 365 или Office 365.

Если вы не используете планы звонков, необходимо перенаправить развертывание корпоративной голосовой связи на прямую маршрутиз телефонная система в рамках обновления до Teams.

Дополнительные сведения см. [в дополнительных сведениях о прямой телефонная система маршрутии.](./direct-routing-landing-page.md) Если вы планируете использовать планы звонков, обратитесь к нашим рекомендациям по переносу номеров телефонов [в](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)Teams.