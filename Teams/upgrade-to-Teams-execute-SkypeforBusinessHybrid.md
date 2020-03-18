---
title: Обновление гибридного развертывания Skype для бизнеса до Microsoft Teams | ТСОП
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Рекомендации по обновлению до Teams из гибридного развертывания Skype для бизнеса.
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
ms.openlocfilehash: ca9ebc7a28e07eec9b24c0628ade4941c0fd2fa2
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706699"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Переход с гибридного развертывания Skype для бизнеса на Teams

![Этапы поездки на обновление, акцент на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")

Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению. Перед продолжением убедитесь, что выполнены следующие действия:

- [Вовлеченные заинтересованные лица в проект](upgrade-enlist-stakeholders.md)
- [Определение области охвата проекта](https://aka.ms/SkypetoTeams-Scope)
- [Сосуществование и взаимодействие Skype для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбрано путешествие с обновлением](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Подготовка среды](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Подготовка Организации](https://aka.ms/SkypeToTeams-UserReadiness)
- [Пробные испытания](https://aka.ms/SkypeToTeams-Pilot)

Следуйте указаниям, приведенным в этой статье, если вы развернули Skype для бизнеса или Microsoft Lync в локальной среде и настроили ее в гибридном развертывании с вашим клиентом Office 365, и ваша организация хочет выборочно выполнить обновление для Teams с помощью нескольких режимы сосуществования — или все. Если вы хотите провести обновление, вам нужно будет переносить пользователей в Skype для бизнеса Online (если они еще не подключены к сети), а затем назначить им подходящий режим сосуществования и обновления.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Шаг 1: перемещение пользователей в Skype для бизнеса Online

Это действие распространяется на пользователей, которые в настоящее время размещены в локальной среде. Дополнительные сведения о переносе этих пользователей в Skype для бизнеса Online можно найти [в разделе Перемещение пользователей из локальной сети в Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Действие 2: назначение режима сосуществования и обновления

После того как вы перенесли пользователей в Skype для бизнеса Online, вы можете назначить им режим совместного существования, основываясь на пути обновления, который выбрала ваша организация. Дополнительные сведения можно найти [в статье Настройка параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [теамсупградеполици: управление миграцией и сосуществованием](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> С помощью Skype для бизнеса Server 2019 и будущего накопительного обновления для Skype для бизнеса Server 2015 вы сможете выполнить шаг 1 (перемещение пользователей в Skype для бизнеса Online) и шаг 2 (обновление пользователей до Teams). Дополнительные сведения будут предоставлены после выпуска Skype для бизнеса Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и команды

Если вы переносите гибридное развертывание Skype для бизнеса в телефонную систему с помощью планов звонков, а Microsoft является поставщиком услуг коммутируемой телефонной сети (PSTN) и предполагает, что вы выполнили перенос номера телефона, то после обновления пользователей В Teams будут автоматически перенесены входящие звонки через PSTN в Teams.

Если тарифные планы недоступны или вы планируете использовать существующий поставщик подключения по протоколу PSTN, вам нужно перевести свое развертывание по голосовой и гибридной среде, в котором используется существующее локальное развертывание или облачное издание Прямая маршрутизация Microsoft Phone System. Чтобы обновить пользователей до Teams, ознакомьтесь с [дополнительными сведениями о прямой маршрутизации для телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).
