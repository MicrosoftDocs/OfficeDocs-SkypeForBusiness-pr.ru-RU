---
title: PowerShell для базового обновления| Microsoft Teams| Предоставление политики обновления для interop
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о том, как остановить обновление до Microsoft Teams, если Центр администрирования не был освещен в вашем клиенте.
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809099"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Переход с Skype для бизнеса Online на Microsoft Teams

> [!Note]
> Описанные в этой статье команды предназначены для использования в контрольном списке ["Базовая](https://aka.ms/UpgradeBasic) обновление".

Аспекты технической миграции при обновлении необходимо уведомить пользователей о том, что Skype для бизнеса будет обновляться до Teams, а затем перенано в режим **только Teams.** Эти действия можно выполнить в удаленном сеансе удаленного Windows PowerShell Skype для Windows PowerShell центре администрирования Microsoft Teams.

Мы активно развертываем средства обновления в Центре администрирования [Microsoft Teams,](manage-teams-skypeforbusiness-admin-center.md)и они должны стать доступны в ближайшее время в вашем клиенте. Как только она станет доступна, сведения о переносе пользователей можно найти в параметрах сосуществования и [обновления.](https://aka.ms/SkypeToTeams-SetCoexistence)

Если вы готовы к обновлению, воспользуйтесь командами [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) перечисленными в таблице ниже.

| Шаг "Основные обновления" # | Режим | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Уведомить пользователя Skype для бизнеса<br>(Используйте эту команду, если пользователи находятся **в** режиме "Острова" (по умолчанию)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Например, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Только Skype для бизнеса + Уведомление пользователя Skype для бизнеса <br>(Используйте эту команду, если пользователи в настоящее время находятся в **режиме только Skype для** бизнеса) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Только в Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
