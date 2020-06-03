---
title: Основное обновление оболочки PowerShell | Microsoft Teams | Предоставление политики взаимодействия по обновлению
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о том, как stopgap обновить приложение до Microsoft Teams, если в вашем клиенте не горит центр администрирования.
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
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Обновление пользователей из Skype для бизнеса Online в Microsoft Teams

> [!Note]
> Команды, описанные в этой статье, предназначены для использования в качестве части базового контрольного списка [обновления](https://aka.ms/UpgradeBasic) .

Благодаря техническим аспектам миграции ваши пользователи получат уведомление о том, что Skype для бизнеса будет обновлен до Teams, а затем перейдет в режим " **только для Team** ". Эти действия можно выполнить с помощью удаленного сеанса Windows PowerShell в Skype для бизнеса или через центр администрирования Microsoft Teams.

Мы активно выстраиваете средства обновления в [центре администрирования Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md), и он должен быть доступен только в вашем клиенте. По мере их появления вы можете найти сведения о переносе пользователей с [помощью настройки сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence).

Если вы готовы обновить уже сегодня, вы можете использовать команды [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) , указанные в приведенной ниже таблице.

| Основные действия по обновлению # | Режиме | Команда PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | О-ва + уведомление пользователей Skype для бизнеса<br>(Используйте эту команду, если в настоящее время пользователи находятся в режиме " **острова** " (по умолчанию)). | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(например, $SipAddress = "TestUser@contoso.com")* |
| [5](upgrade-basic.md#step-5) | Только Skype для бизнеса + уведомление пользователей Skype для бизнеса <br>(Используйте эту команду, если в настоящее время пользователи находятся в режиме " **только Skype для бизнеса** "). | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Только для Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
