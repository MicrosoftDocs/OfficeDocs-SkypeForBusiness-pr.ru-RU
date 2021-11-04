---
title: PowerShell для базового обновления| Microsoft Teams| Политика "Предоставить обновление во время обновления"
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о стоп-запросе на обновление до Microsoft Teams если Центр администрирования не загорелся в вашем клиенте.
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
ms.openlocfilehash: a281a835240db1ee61959e468eb868e833878f16
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762947"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Обновление пользователей с Skype для бизнеса Online до Microsoft Teams

> [!Note]
> Команды, описанные в этой статье, предназначены для использования в контрольном списке [Обновить](./upgrade-start-here.md) базовую.

В зависимости от аспектов технической миграции необходимо уведомить пользователей о том, Skype для бизнеса будет обновлен  до Teams, а затем Teams режиме. Эти действия можно выполнить в Skype для бизнеса удаленного Windows PowerShell или через центр Microsoft Teams администрирования.

Мы активно развертываем средства обновления в Центре администрирования Microsoft Teams [,](manage-teams-skypeforbusiness-admin-center.md)и они должны стать доступны в ближайшее время в вашем клиенте. Как только она станет доступна, вы сможете найти сведения о переносе пользователей в настройках сосуществования и [обновления.](./setting-your-coexistence-and-upgrade-settings.md)

Если вы готовы к обновлению уже сегодня, воспользуйтесь командами [PowerShell,](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) перечисленными в таблице ниже.

| Шаг "Обновить базовый" # | Режим | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Уведомить Skype для бизнеса пользователя<br>(Используйте эту команду, если пользователи сейчас находятся в режиме **"Острова"** (по умолчанию)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Например, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype для бизнеса Только + Уведомить Skype для бизнеса пользователя <br>(Используйте эту команду, если пользователи сейчас находятся **Skype для бизнеса режиме)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Только | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |