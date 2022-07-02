---
title: Базовое обновление PowerShell| Microsoft Teams| Предоставление политики взаимодействия при обновлении
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Сведения о стоп-коде для обновления до Microsoft Teams, если Администратор центр не загорелась в клиенте.
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606038"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Обновление пользователей с Skype для бизнеса Online до Microsoft Teams

> [!Note]
> Команды, описанные в этой статье, предназначены для использования в контрольном списке [upgrade Basic](./upgrade-start-here.md) .

Аспекты технической миграции при обновлении влечет за собой уведомление пользователей о том, Skype для бизнеса будут обновлены до Teams, а затем переводят их в режим **"Только Teams**". Эти действия можно выполнить с помощью Skype для бизнеса удаленного Windows PowerShell или центра администрирования Microsoft Teams.

Мы активно развертываем средства обновления в Центре администрирования [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md), и они должны появиться в ближайшее время в вашем клиенте. Как только она станет доступна, вы сможете найти сведения о миграции пользователей в разделе "Настройка параметров сосуществования и [обновления"](./setting-your-coexistence-and-upgrade-settings.md).

Если вы готовы выполнить обновление уже сегодня, можно использовать команды [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) , перечисленные в следующей таблице.

| Шаг "Обновить базовый" # | Режим | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype для бизнеса User<br>(Используйте эту команду, если пользователи в настоящее время находятся в режиме **"Острова** " (по умолчанию)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(например, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype для бизнеса только + уведомить Skype для бизнеса пользователя <br>(Используйте эту команду, если пользователи в настоящее время **находятся в Skype для бизнеса режиме**) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Только Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |