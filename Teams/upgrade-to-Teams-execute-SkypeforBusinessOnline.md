---
title: Обновление от Скайп для бизнеса в Интернете для групп - группами Майкрософт
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Вопросы, касающиеся обновления группы из Скайп для бизнеса в Интернет
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: fabcd88a0444a01f950064ade0c49dfef50400e1
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013573"
---
![Этапы обновления пути с акцентом на развертывание и стадии реализации] (media/upgrade-banner-deployment.png "Этапы обновления пути с акцентом на развертывание и стадии реализации")

В этой статье является частью развертывания и внедрения этапа обновления пути. Прежде чем продолжить, убедитесь, что вы выполните следующие действия:

-   [Прикреплено другие заинтересованные стороны проекта](upgrade-enlist-stakeholders.md)
-   [Определенные области проекта](https://aka.ms/SkypetoTeams-Scope)
-   [Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
-   [Выбранные обновления пути](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Подготовка среды](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Подготовлено вашей организации](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Проведение пилотного проекта](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Обновление от Скайп для бизнеса в Интернете по группам

Следуйте указаниям в этой статье, если полностью развернут Скайп для бизнеса в Интернет и требуется обновление пользователей с Скайп для бизнеса в группы. Можно обновить пользователей выборочно или файловый, основанным на обновление journey, ваша организация решила, назначив соответствующие сосуществования и обновления режима для пользователей.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Назначение режима совместимости и обновления

Обновление до команды может быть выполнена с назначением режим TeamsOnly TeamsUpgradePolicy, который может выполняться с помощью групп Майкрософт & Скайп для бизнеса центра администрирования или Скайп для бизнеса удаленного сеанса Windows Powershell.

Для получения дополнительных сведений см [Задание вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграция и сосуществование](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системой и рабочих групп

Если ваше Скайп для бизнеса в Интернет развертывания включает в себя телефонной системы с помощью вызова планы и Microsoft — это ваш поставщик телефонной сети (общего пользования PSTN), обновление пользователей группам автоматический переход входящих PSTN, вызов к группам.

Если ваше Скайп для бизнеса в Интернет развертывания включает системы Phone Edition соединителя облако с, см.в [Дополнительные вопросы для прямой маршрутизации телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).