---
title: Краткое руководство по настройке планов звонков
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Краткое руководство по настройке планов звонков в Microsoft Teams для настройки набора пользователей.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a222dd7734fd8df3885b0601a5e511d1936922a3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726418"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams

Это руководство поможет вам настроить набор пользователей, чтобы они могли изучить планы звонков в Teams.

Ознакомьтесь с объявлением о планах звонков от 12 декабря 2017 г. в [Teams:](https://aka.ms/ipyqus) интеллектуальные средства связи при звонках в Teams

> [!NOTE]
> Мы рекомендуем параллельно с этим кратким руководством [](calling-plan-landing-page.md) ознакомиться с телефонная система с [](https://aka.ms/cloudvoice) планами звонков и FastTrack, чтобы спланировать и добиться успешного раздатки.

Добавив планы звонков Microsoft 365 и Office 365 на платформе Skype для бизнеса, вы сможете использовать Teams для телефонных звонков на мобильные и на мобильные телефоны и на мобильные телефоны через телефонную сеть общего пользования (STN).

![Снимок экрана: страница "Контакты" в Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Необходимые условия для включения **вкладки Звонки** в Teams
Чтобы включить **вкладку** Звонки в Teams для пользователей должны быть включены 1:1 звонки в Teams и использовать клиент Teams, который поддерживает Teams звонков 1:1. Чтобы узнать, как управлять звонками 1:1 в Teams, ознакомьтесь со статьей [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy) Чтобы узнать, какие клиенты поддерживают вызовы, ознакомьтесь со статьей Ограничения и [спецификации для](./limits-specifications-teams.md)Microsoft Teams.

> [!NOTE]
> В настоящее время голосовая почта недоступна на вкладке Звонки, если только пользователь не включен для звонков по ННР. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Необходимые условия для включения панели **набора номера** в Teams
Чтобы включить **вкладку** Панель набора номера в Teams и разрешить пользователям звонить и принимать звонки по ЗВОНКОВ по ЗВОНКОВ, необходимо телефонная система пользователей для планов звонков и телефонных вызовов. Чтобы узнать, как настроить планы звонков, ознакомьтесь со статьей [Настройка планов звонков.](./set-up-calling-plans.md)
Кроме того, для Teams пользователей необходимо включить в политику Teams звонков "Разрешить Teams звонков". Дополнительные [сведения см. в Teams](./manage-teams-skypeforbusiness-admin-center.md) управления переходом на новую Microsoft Teams администрирования.
> [!NOTE]
> Вы также можете использовать прямую маршрутику, чтобы разрешить пользователям звонить и принимать звонки по ННР. Чтобы узнать, как настроить прямую маршрутику, ознакомьтесь со ссылкой [Настройка прямой маршрутии.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Использование TeamsUpgradePolicy для управления местом звонков
Чтобы управлять тем, будут ли входящие звонки (и чаты) перенаправлены в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя Центр [](/powershell/module/skype) администрирования [Microsoft Teams](https://aka.ms/teamsadmincenter) или удаленный сеанс Windows PowerShell с командлетами Skype для бизнеса.


По умолчанию TeamsUpgradePolicy имеет вид Islands, который гарантирует, что существующие бизнес-процессы не будут прерываться во время Teams развертывания. По умолчанию voIP, STN и федеражные звонки пользователям будут перенаправлены на Skype для бизнеса до тех пор, пока вы не обновите политику, чтобы включить входящие звонки Teams.  Когда получатели находятся в режиме островов:

 - Входящие вызовы VOIP, Skype для бизнеса в клиенте Skype для бизнеса получателя.
 - Входящие вызовы VOIP, Teams в Teams, если отправитель и получение находятся *в одном клиенте.*
 - Входящие федератированные вызовы VOIP (независимо от того, какой клиент задается) и звонки по ПСПУ всегда перенаправят на Skype для бизнеса клиента Skype для бизнеса получателя.
 
Чтобы обеспечить постоянное перенастройку входящих вызовов VOIP и ПСПУ в клиенте Teams пользователя, обновите его режим совместной работы с TeamsOnly (то есть назначьте ему экземпляр UpgradeToTeams teamsUpgradePolicy).  Дополнительные сведения о режимах совместной работы и TeamsUpgradePolicy см. в руководстве по миграции и совместному использованию Teams и [Skype для бизнеса](./migration-interop-guidance-for-teams-with-skype.md)

**ЗАМЕТКИ**
 - Skype для бизнеса IP-телефоны будут принимать звонки, даже если пользователь находится в режиме TeamsOnly.  
 - Пользователи, имеющие лицензии на телефонная система и планы звонков для использования с Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут иметь вкладку Звонки в Teams и могут звонить из Teams без административных действий администраторов.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Настройка того, как настроить прием всех входящих звонков по VOIP и ПСN в Teams
Чтобы обеспечить прием всех входящих звонков voIP и ЗВОНКОВ по ПСПУ в Teams, задайте для них режим совместной работы в Центре администрирования Microsoft Teams Или используйте сеанс Skype для бизнеса удаленного Windows PowerShell для обновления TeamsUpgradePolicy следующим образом:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>См. также
[Настройка планов звонков](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](./migration-interop-guidance-for-teams-with-skype.md)

[Телефонная система с тарифными планами](calling-plan-landing-page.md)

[Skype для бизнеса Справочник по cmdhell PowerShell](/powershell/module/skype)
