---
title: Краткое руководство по настройке планов звонков
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Краткое руководство по настройке планов звонков Microsoft Teams для настройки набора пользователей.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeb9fae94d186e841cdacbd05879ab2891b9ba2a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745695"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams

Это руководство поможет вам настроить набор пользователей, чтобы они могли изучить планы звонков в Teams.

Ознакомьтесь с объявлением о планах звонков от 12 декабря 2017 г. в Teams. Интеллектуальные коммуникации— следующий шаг при вызове в [Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Мы рекомендуем параллельно с этим кратким руководством [](calling-plan-landing-page.md) ознакомиться с телефонная система с [](https://aka.ms/cloudvoice) планами звонков и FastTrack, чтобы спланировать и добиться успешного раздатки.

Добавив планы звонков — функции Microsoft 365 и Office 365 на платформе Skype для бизнеса, — теперь вы можете использовать Teams для телефонных звонков на мобильные и на мобильные телефоны и на мобильные телефоны через ПСПС.

![Снимок экрана: страница "Контакты" в Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Необходимые условия для включения **вкладки Звонки** в Teams
Чтобы включить **вкладку** Звонки в Teams пользователям необходимо включить в Teams звонков 1:1 и использовать клиент Teams, который поддерживает Teams звонков 1:1. Чтобы узнать, как управлять звонками 1:1 в Teams, ознакомьтесь со статьей [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy) Чтобы узнать, какие клиенты поддерживают вызовы, ознакомьтесь со статьей Ограничения [и спецификации для](./limits-specifications-teams.md)Microsoft Teams.

> [!NOTE]
> В настоящее время голосовая почта недоступна на вкладке Звонки, если только пользователь не включен для звонков по ЗВОНКОВ по ННР. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Необходимые условия для включения панели **набора** номера в Teams
Чтобы включить **вкладку** Панель набора номера в Teams и разрешить пользователям звонить и принимать звонки по ЗВОНКОВ по ЗВОНКОВ, необходимо телефонная система и планы звонков. Чтобы узнать, как настроить планы звонков, ознакомьтесь со статьей [Настройка планов звонков.](./set-up-calling-plans.md)
Кроме того, для Teams пользователей необходимо включить в политику Teams звонков "Разрешить Teams звонков". Дополнительные [сведения см. в Teams](./manage-teams-skypeforbusiness-admin-center.md) управления переходом на новую Microsoft Teams администрирования.
> [!NOTE]
> Вы также можете использовать прямую маршрутику, чтобы разрешить пользователям звонить и принимать звонки по ННР. Чтобы узнать, как настроить прямую маршрутику, ознакомьтесь со ссылкой [Настройка прямой маршрутии.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Использование TeamsUpgradePolicy для управления местом звонков
Чтобы контролировать, будут ли входящие звонки (и чаты) перенаправлены в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя Центр [](/powershell/module/skype) администрирования [Microsoft Teams](https://aka.ms/teamsadmincenter) или удаленный сеанс Windows PowerShell с Skype для бизнеса Командлеты.


По умолчанию TeamsUpgradePolicy имеет вид Islands, который гарантирует, что существующие бизнес-процессы не будут прерываться во время Teams развертывания. По умолчанию voIP, STN и федераированные звонки пользователям будут продолжать перенаправление на Skype для бизнеса до тех пор, пока вы не обновите политику, чтобы включить входящие звонки Teams.  Когда получатели находятся в режиме островов:

 - Входящие вызовы VOIP, Skype для бизнеса в клиенте Skype для бизнеса получателя.
 - Входящие вызовы VOIP, Teams в Teams, если отправитель и приемник находятся *в одном клиенте.*
 - Входящие федератированные вызовы VOIP (независимо от того, какой клиент задается) и звонки по ПСПУ всегда перенаправят на Skype для бизнеса клиента получателя.
 
Чтобы обеспечить постоянное переназначение входящих вызовов VOIP и ПСПУ в клиенте Teams пользователя, обновите его режим совместной работы с TeamsOnly (то есть назначьте ему экземпляр UpgradeToTeams teamsUpgradePolicy).  Дополнительные сведения о режимах сосуществования и TeamsUpgradePolicy см. в руководстве по миграции и совместному использованию данных для организаций, использующих Teams совместно с Skype для бизнеса [](./migration-interop-guidance-for-teams-with-skype.md)

**ЗАМЕТКИ**
 - Skype для бизнеса IP-телефоны будут принимать звонки, даже если пользователь находится в режиме TeamsOnly.  
 - Пользователи, имеющие лицензии на телефонная система и планы звонков для использования с Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут иметь вкладку Звонки в Teams и могут звонить из Teams, не принимая никаких административных действий.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Настройка того, как настроить прием всех входящих звонков по voIP и ПСN в Teams
Чтобы обеспечить пользователям прием всех входящих звонков voIP и ПСN в Teams, задайте для них режим сосуществования в TeamsOnly в Центре администрирования Microsoft Teams или используйте сеанс Skype для бизнеса удаленного Windows PowerShell для обновления TeamsUpgradePolicy следующим образом:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>См. также
[Настройка планов звонков](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](./migration-interop-guidance-for-teams-with-skype.md)

[Телефонная система с тарифными планами](calling-plan-landing-page.md)

[Skype для бизнеса Справочник по cmdlet(ссылка) PowerShell](/powershell/module/skype)
