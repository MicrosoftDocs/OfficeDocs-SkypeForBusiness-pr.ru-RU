---
title: Краткое руководство по началу работы. Настройка планов звонков
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Краткое руководство по настройке планов звонков в Microsoft Teams для запуска набора пользователей.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789584"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams

Это руководство поможет вам настроить и выполнить набор пользователей, чтобы они могли изучить планы звонков в Teams.

Прочитайте объявление о планах звонков в Teams от 12 декабря 2017 г. [](https://aka.ms/ipyqus)

> [!NOTE]
> Мы рекомендуем параллельно с этим кратким руководством прочитать телефонную систему с планами звонков и [FastTrack](https://aka.ms/cloudvoice), чтобы спланировать и обеспечить успешное развертывание.[](calling-plan-landing-page.md)

Добавив планы звонков — компонент Microsoft 365 и Office 365 на платформе Skype для бизнеса, вы можете использовать Teams для телефонных звонков и телефонных линий и мобильных телефонов через общедоступную телефонную сеть (ТСОП).

![Снимок экрана: страница "Контакты" в Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Необходимые условия для включения вкладки **"Вызовы** " в Teams
Чтобы включить **вкладку "** Звонки" в Teams, пользователям необходимо включить вызовы 1:1 в Teams и использовать клиент Teams, который поддерживает вызовы Teams 1:1. Сведения об управлении вызовами 1:1 в Teams см. в [разделе Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Сведения о том, какие клиенты поддерживают вызовы, см. в описании ограничений и [спецификаций для Microsoft Teams](./limits-specifications-teams.md).

> [!NOTE]
> В настоящее время голосовая почта не будет доступна на вкладке "Вызовы", если пользователь не включен для звонков по ТСОП. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Необходимые условия для включения панели набора **номера** в Teams
Чтобы включить **вкладку "** Панель набора номера" в Teams и разрешить пользователям совершать и принимать звонки по ТСОП, необходимо подготовить пользователей для телефонной системы и планов звонков. Сведения о настройке планов звонков см. в статье ["Настройка планов звонков"](./set-up-calling-plans.md).
Кроме того, только для пользователей Teams необходимо убедиться, что в политике звонков Teams включен параметр "Разрешить частные звонки". Дополнительные сведения см. в разделе "Управление Teams" во время перехода [в новый Центр администрирования Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md) .
> [!NOTE]
> Вы также можете использовать прямую маршрутизацию, чтобы разрешить пользователям совершать и принимать звонки по ТСОП. Сведения о настройке прямой маршрутизации см. в статье ["Настройка прямой маршрутизации"](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Использование TeamsUpgradePolicy для управления расположением звонков
Чтобы управлять входящими звонками (и чатами) в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя Центр администрирования [Microsoft Teams](https://aka.ms/teamsadmincenter) или удаленный сеанс Windows PowerShell с Skype для бизнеса командлетами.[](/powershell/module/skype)


Конфигурация TeamsUpgradePolicy по умолчанию — это режим Islands, который предназначен для обеспечения того, чтобы существующие рабочие процессы не прерывались во время развертывания Teams. По умолчанию voIP, ТСОП и федеративные вызовы для пользователей будут по-прежнему перенаправляться в Skype для бизнеса пока вы не обновите политику, чтобы включить входящие вызовы в Teams.  Когда получатели находятся в режиме островов:

 - Входящие вызовы VOIP, которые поступили Skype для бизнеса всегда выполняются в клиенте Skype для бизнеса получателя.
 - Входящие вызовы VOIP, которые поступили в Teams, выполняются в Teams, если отправитель и получатель *находятся в одном клиенте*.
 - Входящие федеративные VOIP (независимо от того, какой клиент исходит) и вызовы ТСОП всегда поступают Skype для бизнеса клиента получателя.
 
Чтобы обеспечить постоянное размещение входящих вызовов VOIP и ТСОП в клиенте Teams пользователя, обновите режим сосуществования пользователя на TeamsOnly (то есть назначьте ему экземпляр UpgradeToTeams TeamsUpgradePolicy).  Дополнительные сведения о режимах сосуществования и TeamsUpgradePolicy см. в руководстве по миграции и взаимодействию для организаций, использующих [Teams](./migration-interop-guidance-for-teams-with-skype.md) вместе с Skype для бизнеса

**ЗАМЕТКИ**
 - Skype для бизнеса IP-телефоны будут принимать звонки, даже если пользователь находится в режиме TeamsOnly.  
 - Пользователи, которым были предоставлены лицензии на телефонную систему и планы звонков для использования с Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут иметь вкладку "Звонки" в Teams и могут выполнять исходящие звонки по ТСОП из Teams без каких-либо административных действий администраторов.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Настройка пользователей для получения всех входящих вызовов VOIP и ТСОП в Teams
Чтобы пользователи могли получать все входящие вызовы VOIP и ТСОП в Teams, задайте режим сосуществования пользователя TeamsOnly в Центре администрирования Microsoft Teams или используйте Skype для бизнеса удаленный сеанс Windows PowerShell для обновления TeamsUpgradePolicy следующим образом:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>См. также
[Настройка планов звонков](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](./migration-interop-guidance-for-teams-with-skype.md)

[Телефонная система с тарифными планами](calling-plan-landing-page.md)

[Skype для бизнеса командлета PowerShell](/powershell/module/skype)
