---
title: PowerShell для базового обновления| Microsoft Teams| Политика "Предоставить обновление во время обновления"
author: HowlinWolf-92
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
ms.openlocfilehash: 1f6fc4ade75e7ee954104fe723751b5ef6d4ccca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830753"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Обновление пользователей с Skype для бизнеса Online до Microsoft Teams

> [!Note]
> Команды, описанные в этой статье, предназначены для использования в контрольном списке [Обновить](./upgrade-start-here.md) базовую.

При технической миграции необходимо уведомить пользователей о том, Skype для бизнеса будет обновлен до Teams а затем перенавести их в **Teams** режим. Эти действия можно выполнить с помощью Skype для бизнеса удаленного Windows PowerShell или через центр Microsoft Teams администрирования.

Мы активно развертываем средства обновления в Центре администрирования Microsoft Teams [,](manage-teams-skypeforbusiness-admin-center.md)и они должны быть доступны в ближайшее время в вашем клиенте. Как только она станет доступна, вы сможете найти сведения о переносе пользователей в настройках сосуществования и [обновления.](./setting-your-coexistence-and-upgrade-settings.md)

Если вы готовы к обновлению уже сегодня, воспользуйтесь командами [PowerShell,](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) перечисленными в таблице ниже.

| Шаг "Обновить базовый" # | Режим | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype для бизнеса User<br>(Используйте эту команду, если пользователи сейчас находятся в режиме **"Острова"** (по умолчанию)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Например, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype для бизнеса Только + Уведомить Skype для бизнеса пользователя <br>(Используйте эту команду, если пользователи сейчас находятся **в Skype для бизнеса режиме)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Только | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |