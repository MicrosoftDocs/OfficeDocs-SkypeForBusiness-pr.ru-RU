---
title: Переход с локальной среды Skype для бизнеса на Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как перевести организацию в Microsoft Teams из локального Skype для бизнеса развертывания.
ms.localizationpriority: medium
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615445"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Переход с Skype для бизнеса локального развертывания на Teams

![Этапы пути обновления с акцентом на этап развертывания и реализации.](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этап развертывания и реализации")

Эта статья является частью этапа развертывания и реализации процесса обновления. Прежде чем продолжить, убедитесь, что вы выполнили следующие действия:

- [Прикрепление заинтересованных лиц проекта](upgrade-enlist-stakeholders.md)
- [Определение области проекта](./upgrade-define-project-scope.md)
- [Понимание сосуществования и взаимодействия Skype для бизнеса и Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Выбор пути обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовка среды](./upgrade-prepare-environment.md)
- [Подготовка организации](./upgrade-prepare-organization.md)
- [Проводит пилотный проект](./pilot-essentials.md)

Следуйте указаниям, приведенным в этой статье, если вы развернули Skype для бизнеса или Microsoft Lync в локальной среде и ваша организация хочет выполнить обновление до Microsoft Teams выборочно с помощью нескольких режимов сосуществования или в режиме "вся". 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Шаг 1. Развертывание гибридного подключения

Ключевым предварительным требованием для обновления пользователей до Teams является развертывание гибридного подключения.

Дополнительные сведения см. в статье ["Развертывание гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online"](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Шаг 2. Реализация выбранного пути обновления для организации

После завершения гибридной настройки вы можете запланировать перемещение пользователей в Microsoft 365 или Office 365.

Дополнительные сведения см. в следующих статьях:

- [TeamsUpgradePolicy: управление миграцией и сосуществованием](upgrade-to-teams-on-prem-tools.md).

- [Перемещение пользователей из локальной среды в Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и Teams

Переход с локальных телефонных систем на Teams позволит вам воспользоваться преимуществами прямой маршрутизации телефонной системы (прямая маршрутизация) или предоставленных корпорацией Майкрософт планов звонков для Microsoft 365 или Office 365.

Если вы не используете планы звонков, необходимо перевести корпоративное голосовое развертывание на прямую маршрутизацию телефонной системы в рамках обновления до Teams.

Дополнительные сведения см [. в дополнительных рекомендациях по прямой маршрутизации телефонной системы](./direct-routing-landing-page.md). Если вы планируете использовать планы звонков, обратитесь к нашим рекомендациям по переносу телефонных [номеров в Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).