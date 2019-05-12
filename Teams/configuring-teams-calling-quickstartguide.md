---
title: Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Краткое руководство по настройке планов звонков в Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd1e9484b522a657a92916815c1ae8940dcc2117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898525"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
==============================================================

Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.

Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)

> [!NOTE]
> Рекомендуется, параллельно с краткое руководство прочитать [Телефонной системы с помощью вызова планы](calling-plan-landing-page.md) и [она](https://aka.ms/cloudvoice) плану и диск успешного развертывания.

За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).

![Звонки в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Что необходимо для активации вкладки **Звонки** в Teams
Включение вкладки **звонки** в группах пользователи должны иметь 1:1 вызов включено в группах и с помощью команды клиента, вызов команд 1:1. Чтобы узнать, как управлять 1:1 вызов в группах, прочитайте [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Чтобы узнать, какие клиенты поддерживают вызова, ознакомьтесь с [ограничения и характеристики для групп Майкрософт](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> На данный момент голосовой почты не будут доступны в вкладке звонки, если пользователь включен для вызовов ТСОП. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Необходимые условия для включения панель **Набора номера** в группах
Для включения вкладки **Панели набора номера** в группах и разрешить пользователям выполнение и прием звонков ТСОП необходимо будет к подготовке пользователей для телефонной системой и вызов планов. Чтобы узнать, как настраивать вызове планы, прочитайте [Set up вызов планы](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Можно также использовать прямой маршрутизации, чтобы разрешить пользователям выполнение и прием звонков ТСОП. Чтобы узнать, как настроить прямой маршрутизации, прочитайте [Настройка прямой маршрутизации](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Использование TeamsUpgradePolicy для элемента управления, где land звонки
Чтобы управлять ли входящие звонки (и беседы) land в группы или Скайп для бизнеса, Администраторы используют TeamsUpgradePolicy, с помощью любого из [групп Майкрософт центра администрирования](https://aka.ms/teamsadmincenter) или с помощью удаленного сеанса Windows PowerShell с [Скайп для бизнеса](https://docs.microsoft.com/powershell/module/skype) командлеты.


Конфигурация по умолчанию TeamsUpgradePolicy является острова режим, в котором разработан для обеспечения, существующего бизнес-рабочие процессы не прерывается во время развертывания групп. По умолчанию VoIP, ТСОП и федеративных вызовов для пользователей будет направляться в Скайп для бизнеса до обновления политики, включающей входящих звонков для группы.  Когда получатели находятся в режиме о-ва:

 - Входящие VOIP вызывает этот происхождение в Скайп Business всегда Земля в Скайп получателя для клиента Business.
 - Входящие VOIP вызывает, которая была создана в land группами в группах, *Если отправитель и получатель, тому же владельцу*.
 - Входящая федеративных VOIP, (независимо от того, какой компьютер исходит) и вызовы PSTN всегда Земля в Скайп получателя для клиента Business.
 
Чтобы гарантировать, что входящие VOIP и PSTN вызывает всегда Земля в группы клиента, обновите режиме сосуществования пользователя быть TeamsOnly (это значит, назначить их экземпляр TeamsUpgradePolicy «UpgradeToTeams».  Дополнительные сведения о режимах сосуществования и TeamsUpgradePolicy можно [миграции и руководство по взаимодействию для организаций, с помощью команды Скайп для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**ПРИМЕЧАНИЯ**
 - Скайп для бизнеса IP-телефонов будет принимать звонки, даже в том случае, если пользователь находится в режиме TeamsOnly.  
 - Пользователи, которые были созданы с телефонной системой и вызов планов лицензии для использования с Скайп для бизнеса в Интернет (например назначенные им значение OnlineVoiceRoutingPolicy), будут иметь вкладке звонков включен в группах и вводятся исходящие вызовы ТСОП из Группы без необходимости никаких административных действий Администраторы.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Как настроить пользователям принимать все входящие VOIP и PSTN вызывает в группах
Чтобы убедиться, что пользователи получают все входящие звонки VOIP и ТСОП в группах, нужно выбрать режим пользователя сосуществования TeamsOnly в центре администрирования группами Майкрософт, или использовать Скайп для бизнеса удаленного сеанса Windows PowerShell для обновления TeamsUpgradePolicy следующим образом:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>См. также
[Настройка планов звонков](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Система телефон с Тарифные планы](calling-plan-landing-page.md)

[Скайп для Справочник командлетов PowerShell бизнеса](https://docs.microsoft.com/powershell/module/skype)

