---
title: PowerShell для базового обновления| Microsoft Teams| Политика "Предоставить обновление во время обновления"
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о том, как прекратить обновление до Microsoft Teams если Центр администрирования не загорелся в вашем клиенте.
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
ms.openlocfilehash: 61201e52eabd9a921da432ac7081329a643664c7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628221"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Обновление пользователей с Skype для бизнеса Online до Microsoft Teams

> [!Note]
> Команды, описанные в этой статье, предназначены для использования в контрольном списке [Обновить](./upgrade-start-here.md) базовую.

При технической миграции необходимо уведомить пользователей о том, Skype для бизнеса будет обновлено до Teams а  затем перена которое будет перемещено в Teams режиме. Эти действия можно выполнить в Skype для бизнеса удаленного Windows PowerShell или через Microsoft Teams администрирования.

Мы активно развертываем средства обновления в Центре администрирования Microsoft Teams [и](manage-teams-skypeforbusiness-admin-center.md)скоро оно появится в вашем клиенте. Как только она станет доступна, вы сможете найти сведения о переносе пользователей в настройках сосуществования и [обновления.](./setting-your-coexistence-and-upgrade-settings.md)

Если вы готовы к обновлению уже сегодня, воспользуйтесь командами [PowerShell,](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) перечисленными в таблице ниже.

| Шаг "Обновить базовый" # | Режим | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype для бизнеса user<br>(Используйте эту команду, если пользователи сейчас находятся в режиме **"Острова"** (по умолчанию)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Например, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype для бизнеса Только + Уведомить Skype для бизнеса пользователя <br>(Эта команда используется, если пользователи находятся в Skype для бизнеса **режиме)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Только | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |