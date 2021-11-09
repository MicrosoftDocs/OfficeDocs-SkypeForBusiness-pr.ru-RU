---
title: Обновление Skype для бизнеса гибридного развертывания до Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как обновить организацию до Microsoft Teams из гибридного Skype для бизнеса развертывания.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef173755673cf22ece6c3f8325b2d0392092c1eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840661"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Обновление гибридного Skype для бизнеса до Teams

![Этапы пути обновления с акцентом на этапе развертывания и реализации.](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и внедрения")

Эта статья является частью этапа развертывания и реализации, на этапе обновления. Прежде чем при этом подтверждать, что вы выполнили следующие действия:

- [Привлечение заинтересованных лиц по проекту](upgrade-enlist-stakeholders.md)
- [Определение области проекта](./upgrade-define-project-scope.md)
- [Понятное сосуществование и совместное Skype для бизнеса и Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Выбор пути обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовьте свою среду](./upgrade-prepare-environment.md)
- [Подготовленные организации](./upgrade-prepare-organization.md)
- [Пилотный проект](./pilot-essentials.md)

Следуйте указаниям из этой статьи, если вы развернули локальное развертывание Skype для бизнеса или Microsoft Lync и настроили его в гибридном развертывании с вашей организацией Microsoft 365 или Office 365 и ваша организация хочет перейти на Teams выборочно — с помощью нескольких режимов сосуществования или в режиме "вся". Для любого из этих обновлений необходимо переместить пользователей на веб-сайт Skype для бизнеса Online (если они еще не были дома в Интернете), а затем назначить им соответствующий режим совместной работы и обновления.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Шаг 1. Перемещение пользователей в Skype для бизнеса Online

Этот шаг относится к пользователям, которые сейчас находятся в локальной сети. Дополнительные сведения о перемещении этих пользователей в Skype для бизнеса Online см. в этой Skype для бизнеса [Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Шаг 2. Назначение режима сосуществования и обновления

После того как вы переместите пользователей в Skype для бизнеса Online, вы можете назначить им соответствующий режим сосуществования в зависимости от пути обновления, выбранного вашей организацией. Дополнительные сведения [](./setting-your-coexistence-and-upgrade-settings.md) см. в настройках сосуществования и обновления [и TeamsUpgradePolicy:](upgrade-to-teams-on-prem-tools.md)управление миграцией и сосуществованием.

> [!NOTE]
> В Skype для бизнеса Server 2019 г. и в будущем накопительном обновлении Skype для бизнеса Server 2015 вы сможете выполнить этапы 1 (перемещение пользователей в Skype для бизнеса Online) и Шаг 2 (обновление пользователей до Teams) за один шаг. Дополнительные сведения будут предоставлены Skype для бизнеса Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>телефонная система и Teams обновления

Если вы переходите с гибридного развертывания Skype для бизнеса на телефонная система с помощью планов звонков, а поставщиком услуг телефонной сети общего звонков (STN) будет майкрософт, а при условии, что перенос номеров телефонов завершен, обновление пользователей до Teams автоматически переключит входящие вызовы через Teams.

Если планы звонков недоступны или вы собираетесь использовать существующего поставщика связи через ЗВОНКОВ, необходимо перейти с корпоративного голосового развертывания (или гибридного голосового развертывания, которое использует существующее локальное развертывание или Cloud Connector Edition) на Телефон (Майкрософт) Direct Routing. Чтобы обновить пользователей до Teams, см. дополнительные телефонная система прямой [маршрутии.](./direct-routing-landing-page.md)