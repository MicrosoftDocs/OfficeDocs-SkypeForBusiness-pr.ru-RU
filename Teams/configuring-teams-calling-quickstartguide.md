---
title: 'Краткое руководство: настройка планов звонков'
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
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799769"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
==============================================================

Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.

Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)

> [!NOTE]
> Советуем параллельно с этим кратким руководством прочитать телефонную систему с планами звонков и [fastTrack,](https://aka.ms/cloudvoice) чтобы спланировать успешное раздатку. [](calling-plan-landing-page.md)

Добавив планы звонков — функции Microsoft 365 и Office 365, которые работают на платформе Skype для бизнеса, — теперь вы можете использовать Teams для телефонных звонков на мобильные и на мобильные и на мобильные телефоны или на мобильные телефоны по телефонной сети общего пользования (ПС).

![Снимок экрана: страница "Контакты" в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Что необходимо для активации вкладки **Звонки** в Teams
Чтобы включить вкладку **"Звонки"** в Teams, пользователям необходимо включить 1:1 звонки в Teams и использовать клиент Teams, который поддерживает звонков в Teams 1:1. Чтобы узнать, как управлять вызовами 1:1 в Teams, ознакомьтесь с [командой Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Чтобы узнать, какие клиенты поддерживают вызовы, ознакомьтесь с ограничениями и [спецификациями Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)

> [!NOTE]
> В настоящее время голосовая почта на вкладке "Звонки" недоступна, если только для пользователя не включена возможность звонков по ННР. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Необходимые условия для включения панели **набора номера** в Teams
Чтобы включить **вкладку "Панель** набора номера" в Teams и разрешить пользователям делать и принимать звонки по СТАНД, необходимо обеспечить подготовка пользователей к телефонной системе и планам звонков. Чтобы узнать, как настроить планы звонков, прочитайте [статью "Настройка планов звонков".](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)
Кроме того, для пользователей Teams необходимо включить в политике звонков Teams разрешение личных звонков. Дополнительные [сведения см. в сведениях](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) об управлении Teams во время перехода на новый Центр администрирования Microsoft Teams.
> [!NOTE]
> Вы также можете использовать прямую маршрутику, чтобы разрешить пользователям звонить и принимать звонки по ННР. Чтобы узнать, как настроить прямую маршрутику, ознакомьтесь с тем, [как настроить прямую маршрутику.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Использование TeamsUpgradePolicy для управления местом звонков
Чтобы управлять тем, должны ли входящие звонки (и чаты) понищаться в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя центр администрирования [Microsoft Teams](https://aka.ms/teamsadmincenter) или удаленный Windows PowerShell с командлетами [Skype](https://docs.microsoft.com/powershell/module/skype) для бизнеса.


По умолчанию TeamsUpgradePolicy имеет режим Islands, который гарантирует, что существующие бизнес-процессы не будут прерываться во время развертывания Teams. По умолчанию звонки по VoIP, ННР и федератный вызовы вашим пользователям будут продолжать маршрутироваться в Skype для бизнеса до тех пор, пока вы не обновите политику, чтобы включить входящие звонки в Teams.  Если получатели находятся в режиме островов:

 - Входящие звонки VOIP, которые были произведены в Skype для бизнеса, всегда перенаправят в клиент Skype для бизнеса получателя.
 - Входящие вызовы VOIP, которые были произведены в Teams, находятся в Teams, если отправитель и приемник находятся *в одном клиенте.*
 - Входящие федераированные вызовы VOIP (независимо от того, какой клиент из них поступает) и вызовы по ННР всегда перенаправят в клиент Skype для бизнеса получателя.
 
Чтобы входящие вызовы VOIP и STN всегда были в клиенте Teams пользователя, обновите режим сосуществования пользователя на TeamsOnly (то есть назначьте ему экземпляр UpgradeToTeams) TeamsUpgradePolicy.  Дополнительные сведения о режимах сосуществования и TeamsUpgradePolicy см. в руководстве по миграции и совместной работе организаций, использующих Teams вместе со [Skype для бизнеса.](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**ПРИМЕЧАНИЯ**
 - IP-телефоны Skype для бизнеса будут принимать звонки, даже если пользователь находится в режиме TeamsOnly.  
 - Пользователи, имеющие лицензии на телефонную систему и планы звонков для использования со Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут иметь вкладку "Звонки" в Teams и могут принимать исходящие звонки по STN из Teams без административных действий администраторов.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Настройка пользователей для получения всех входящих вызовов VOIP и STN в Teams
Чтобы обеспечить прием пользователями всех входящих вызовов VOIP и STN в Teams, установите для пользователя режим сосуществования TeamsOnly в Центре администрирования Microsoft Teams или используйте удаленный Windows PowerShell Skype для бизнеса для обновления TeamsUpgradePolicy следующим образом:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>См. также
[Настройка планов звонков](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Телефонная система с тарифными планами](calling-plan-landing-page.md)

[Справочник по с помощью cmdlet для Skype для бизнеса PowerShell](https://docs.microsoft.com/powershell/module/skype)

