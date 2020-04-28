---
title: 'Краткое руководство по началу работы: Настройка планов звонков'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Краткое руководство по настройке планов звонков в Microsoft Teams, чтобы можно было получить доступ к группе пользователей и работать с ними.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 10d52aca36d92029f8ee832be84e6dc7d140f749
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902884"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
==============================================================

Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.

Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)

> [!NOTE]
> Мы рекомендуем использовать в этом руководстве по быстрому запуску, что вы прочитали [телефонную систему с тарифными планами](calling-plan-landing-page.md) и [FastTrack](https://aka.ms/cloudvoice) , чтобы спланировать и устранить успешный выпуск.

За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).

![Снимок экрана, на котором показана страница "Контакты" в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Что необходимо для активации вкладки **Звонки** в Teams
Чтобы включить на вкладке " **звонки** " в разделе "Пользователи Teams" поддержку вызова 1:1 в Teams и использование клиента Teams, поддерживающего вызов 1:1 Teams. Чтобы научиться управлять вызовом 1:1 в Teams, прочтите [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Чтобы получить информацию о том, какие клиенты поддерживают вызов, ознакомьтесь с разделом [ограничения и спецификации для Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> В настоящее время Голосовая почта будет недоступна на вкладке "звонки", если только пользователь не поддерживает звонки по сети PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Предварительные требования для включения **панели набора номера** в Teams
Чтобы включить и использовать в Teams вкладку для **набора номера** , вы должны будете подготавливать пользователей для звонков на телефонную систему и планы звонков. Сведения о том, как настроить планы звонков, читайте в статье [Настройка планов звонков](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).
Кроме того, только для пользователей Teams необходимо убедиться в том, что в политике вызова Teams включена поддержка закрытого вызова. Дополнительные сведения [можно найти в разделе Управление группами на переходе в новый центр администрирования Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) .
> [!NOTE]
> Вы также можете использовать прямую маршрутизацию, чтобы предоставить пользователям возможность звонить и принимать звонки по КТСОП. Чтобы научиться настраивать прямую переадресацию, прочтите параметр [настроить прямую маршрутизацию](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Использование TeamsUpgradePolicy для управления тем, где наземный Звонок
Чтобы указать, будут ли входящие звонки (и разговоры) на землю в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя либо [центр администрирования Microsoft Teams](https://aka.ms/teamsadmincenter) , либо удаленный сеанс Windows PowerShell с помощью командлетов [Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype) .


Настройка по умолчанию TeamsUpgradePolicy — это режим "острова", который предназначен для того, чтобы гарантировать, что существующие бизнес-процессы не прерываются при развертывании Teams. По умолчанию звонки по протоколу VoIP, КТСОП и Федеративные пользователи по-прежнему будут перенаправляться в Skype для бизнеса, пока вы не обновите политику, чтобы включить входящие звонки в Teams.  Если получатели находятся в режиме острова, сделайте следующее:

 - Входящие звонки VOIP, поступающие в Skype для бизнеса, всегда размещаются в клиенте Skype для бизнеса получателя.
 - Входящие звонки VOIP, созданные в Teams Land в Teams, *если отправитель и получатель находятся в одном и том же клиенте*.
 - Входящий федеративных VOIP (вне зависимости от того, какой клиент является источником) и PSTN-звонки всегда поступают в клиенте Skype для бизнеса получателя.
 
Чтобы гарантировать, что входящие звонки VOIP и PSTN всегда помещаются в клиенте Teams пользователя, обновите режим сосуществования пользователя, чтобы он был TeamsOnly (то есть назначьте ему экземпляр "UpgradeToTeams" TeamsUpgradePolicy.  Более подробную информацию о режимах сосуществования и TeamsUpgradePolicy можно найти в [статье Руководство по миграции и взаимодействию для организаций, использующих команды совместно со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**Пуск**
 - IP-телефоны Skype для бизнеса будут получать звонки, даже если пользователь находится в режиме TeamsOnly.  
 - Пользователи, которым были предоставлены лицензии на телефонную систему и планы звонков для использования в Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут использовать вкладку звонки в Teams и смогут разгрузить исходящие звонки PSTN из Teams без участия администратора.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Настройка пользователей для получения входящих звонков по протоколу VOIP и КТСОП в Teams
Чтобы убедиться в том, что пользователи получат все входящие звонки по протоколу VOIP и PSTN в Teams, установите для пользователя режим сосуществования TeamsOnly в центре администрирования Microsoft Teams или воспользуйтесь удаленным сеансом Windows PowerShell в Skype для бизнеса, чтобы обновить TeamsUpgradePolicy следующим образом.

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>См. также
[Настройка планов звонков](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Телефонная система с планами звонков](calling-plan-landing-page.md)

[Справочник по командлетам PowerShell в Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype)

