---
title: Обновление Skype для бизнеса гибридного развертывания до Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как обновить организацию до Microsoft Teams с Skype для бизнеса гибридного развертывания.
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
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615605"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Переход с Skype для бизнеса гибридного развертывания на Teams

![Этапы пути обновления с акцентом на этап развертывания и реализации.](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этап развертывания и реализации")

Эта статья является частью этапа развертывания и реализации процесса обновления. Прежде чем продолжить, убедитесь, что вы выполнили следующие действия:

- [Прикрепление заинтересованных лиц проекта](upgrade-enlist-stakeholders.md)
- [Определение области проекта](./upgrade-define-project-scope.md)
- [Понимание сосуществования и взаимодействия Skype для бизнеса и Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Выбор пути обновления](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовка среды](./upgrade-prepare-environment.md)
- [Подготовка организации](./upgrade-prepare-organization.md)
- [Проводит пилотный проект](./pilot-essentials.md)

Следуйте указаниям в этой статье, если вы развернули Skype для бизнеса или Microsoft Lync в локальной среде и настроите его в гибридном развертывании в организации Microsoft 365 или Office 365 и ваша организация хочет выполнить обновление до Teams либо выборочно, используя несколько режимов сосуществования, либо все. Для любого из этих действий необходимо переместить пользователей в Skype для бизнеса Online (если они еще не размещены в Интернете), а затем назначить им соответствующий режим сосуществования и обновления.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Шаг 1. Перемещение пользователей в Skype для бизнеса Online

Этот шаг применяется к пользователям, которые в настоящее время размещены в локальной среде. Дополнительные сведения о перемещении этих пользователей в Skype для бизнеса Online см. в статье "Перемещение пользователей из локальной среды [в Skype для бизнеса Online"](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Шаг 2. Назначение режима сосуществования и обновления

После перемещения пользователей в Skype для бизнеса Online вы можете назначить им соответствующий режим сосуществования в зависимости от выбранного организацией пути обновления. Дополнительные сведения см. в разделе ["](./setting-your-coexistence-and-upgrade-settings.md) Настройка параметров сосуществования и обновления" и ["TeamsUpgradePolicy:](upgrade-to-teams-on-prem-tools.md) управление миграцией и сосуществованием".

> [!NOTE]
> С Skype для бизнеса Server 2019 и последующим накопительным обновлением Skype для бизнеса Server 2015 вы сможете выполнить шаг 1 (перемещение пользователей в Skype для бизнеса Online) и шаг 2 (обновление пользователей до Teams) за один шаг. Дополнительные сведения будут предоставлены Skype для бизнеса Server 2019 г.

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и Teams

Если вы переносите гибридное развертывание Skype для бизнеса на телефонную систему с планами звонков, а корпорация Майкрософт будет поставщиком телефонной сети общего пользования (ТСОП) и предполагается, что вы завершили перенос номеров телефонов, обновление пользователей в Teams автоматически переводит входящие звонки по ТСОП в Teams.

Если планы звонков недоступны или вы планируете использовать существующий поставщик услуг подключения ТСОП, необходимо перевести корпоративное голосовое развертывание или гибридное голосовое развертывание, использующее существующее локальное развертывание или выпуск Cloud Connector, на прямую маршрутизацию телефонной системы Майкрософт. Чтобы обновить пользователей до Teams, ознакомьтесь с дополнительными рекомендациями по прямой [маршрутизации телефонной системы](./direct-routing-landing-page.md).