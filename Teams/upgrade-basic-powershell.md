---
title: PowerShell для базового обновления| Microsoft Teams| Политика предоставления обновления для interop
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о том, как остановить обновление до Microsoft Teams, если Центр администрирования не загорелся в вашем клиенте.
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
ms.openlocfilehash: d51ff3304aae82f49023bdf461e76e4585cda296
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522482"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Переход с Skype для бизнеса Online на Microsoft Teams

> [!Note]
> Описанные в этой статье команды предназначены для использования в контрольном списке ["Обновить](https://aka.ms/UpgradeBasic) базовую".

Аспекты технической миграции при обновлении необходимо уведомить пользователей о том, что Skype для бизнеса будет обновляться до Teams, а затем перенано в режим **только Teams.** Эти действия можно выполнить в удаленном сеансе удаленного Windows PowerShell Skype для Windows PowerShell центре администрирования Microsoft Teams.

Мы активно развертываем средства обновления в Центре администрирования [Microsoft Teams,](manage-teams-skypeforbusiness-admin-center.md)и они должны стать доступны в ближайшее время в вашем клиенте. Как только она станет доступна, вы найдете сведения о переносе пользователей в параметрах сосуществования и [обновления.](https://aka.ms/SkypeToTeams-SetCoexistence)

Если вы готовы к обновлению, воспользуйтесь командами [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) перечисленными в таблице ниже.

| Шаг "Основные обновления" # | Режим | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Уведомить пользователя Skype для бизнеса<br>(Используйте эту команду, если пользователи находятся **в** режиме "Острова" (по умолчанию)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Например, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Только Skype для бизнеса + Уведомление пользователя Skype для бизнеса <br>(Используйте эту команду, если пользователи в настоящее время находятся в **режиме только Skype для** бизнеса) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Только в Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
