---
title: Обновление гибридного развертывания Skype для бизнеса до Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как обновить организацию до Microsoft Teams с помощью гибридного развертывания Skype для бизнеса.
localization_priority: Normal
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104025"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Обновление гибридного развертывания Skype для бизнеса до Teams

![Этапы пути обновления с акцентом на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")

Эта статья является частью этапа развертывания и внедрения, которое вы на пути обновления. Прежде чем продолжается, подтвердим, что вы выполнили следующие действия:

- [Привлечение заинтересованных лиц проекта](upgrade-enlist-stakeholders.md)
- [Определение области проекта](./upgrade-define-project-scope.md)
- [Понимание сосуществования и совместной работы Skype для бизнеса и Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Вы решили перейти на нее](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовлена среда](./upgrade-prepare-environment.md)
- [Подготовив организацию](./upgrade-prepare-organization.md)
- [Проводится пилотный проект](./pilot-essentials.md)

Следуйте указаниям в этой статье, если вы развернули локальное приложение Skype для бизнеса или Microsoft Lync и настроили его в гибридном развертывании с вашей организацией Microsoft 365 или Office 365 и хотите перейти на Teams выборочно — с использованием нескольких режимов сосуществования или в случае всех. Для обновления необходимо перенести пользователей в Skype для бизнеса Online (если они еще не были дома в Интернете), а затем назначить им соответствующий режим совместной работы и обновления.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Шаг 1. Перемещение пользователей в Skype для бизнеса Online

Этот шаг относится к пользователям, которые сейчас находятся в локальной сети. Дополнительные сведения о перемещении этих пользователей в Skype для бизнеса Online см. в теме "Перемещение пользователей из локальной сети в [Skype для бизнеса Online".](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Шаг 2. Назначение режима сосуществования и обновления

После того как вы переместите пользователей в Skype для бизнеса Online, вы можете назначить им соответствующий режим сосуществования в зависимости от выбранного в организации пути обновления. Дополнительные сведения см. в настройках сосуществования и обновления [и](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy,](upgrade-to-teams-on-prem-tools.md)управляющих миграцией и сосуществованием.

> [!NOTE]
> С помощью Skype для бизнеса Server 2019 и будущим накопительным обновлением Skype для бизнеса Server 2015 вы сможете выполнить шаг 1 (перемещение пользователей в Skype для бизнеса Online) и шаг 2 (обновление пользователей до Teams) одним шагом. Дополнительные сведения будут предоставлены после выпуска Skype для бизнеса Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и Teams

Если вы переходите с гибридного развертывания Skype для бизнеса на телефонную систему с планами звонков, а вашим поставщиком услуг телефонной сети ЗВОНКОВ будет Майкрософт и предполагается, что вы выполнили перенос номеров телефонов, обновление пользователей до Teams автоматически переключит входящие звонки по STN в Teams.

Если планы звонков недоступны или вы намерены использовать существующего поставщика услуг связи через ПС, вам необходимо перейти с корпоративного голосового развертывания (или гибридного голосового развертывания, которое использует существующее локальное развертывание или Cloud Connector Edition) на прямую маршрутизовку телефонной системы Майкрософт. Чтобы обновить пользователей до Teams, см. дополнительные соображения по прямой маршрутике телефонной [системы.](./direct-routing-landing-page.md)