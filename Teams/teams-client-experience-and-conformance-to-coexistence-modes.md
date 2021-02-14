---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Узнайте о впечатлениях от работы клиентов Teams и соответствии с режимами сосуществования (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821029"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Взаимодействие с клиентом Teams и соответствие режимам сосуществования

<a name="about-upgrade-basic"></a>

Режимы сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsColetings) обеспечивают простой и предсказуемый опыт для конечных пользователей при переходе организаций со Skype для бизнеса на Teams.  Для организации, перемещаемой в Teams, режим **"Только Teams"** является конечным пунктом назначения для каждого пользователя, хотя не всем пользователям нужно на должно быть назначено только **Teams** (или любой другой режим) одновременно.  До выхода пользователей в режим TeamsOnly организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые являются только **teams,** и теми, кто еще не является. 

Когда пользователь находится в любом из режимов Skype для бизнеса, все входящие чаты и звонки перенанаются его клиенту Skype для бизнеса. Чтобы избежать путаницы с конечными пользователями и обеспечить правильную маршрутику, функции звонков и чата в клиенте Teams отключаются, когда пользователь находится в любом из режимов Skype для бизнеса. Кроме того, планирование собраний в Teams явным образом отключается, когда пользователи работают в режиме SfBOnly или SfBWithTeamsCollab, и явно включено, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.

Так как присутствие указывает на доступность через чат и вызовы, то при отключке чата и звонков самообнахождение в Teams (т. е. отображение собственного присутствия в клиенте Teams на изображении пользователя) также скрыто. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Изменение доступных функций в клиенте Teams в зависимости от режима

Доступные функции в Teams зависят от режима сосуществования пользователя, настроенного командой TeamsUpgradePolicy. В следующей таблице это поведение резюмирует:

|Режим действия пользователя|Опыт работы в клиенте Teams|
|---|---|
|Любой режим Skype для бизнеса|Отключаются вызовы, чат и само присутствие.|
|SfBWithTeamsCollabAndMeetings|Доступно планирование собраний|
|SfBWithTeamsCollab или SfBOnly<sup>1</sup>|Планирование собраний не доступно|
|||

На снимках экрана ниже показано, чем отличаются режимы **Teams и** **"Только** острова", а также все остальные режимы. Обратите внимание, что значки чата и  звонков по умолчанию доступны в режиме "Только **Teams"** или "Острова" (снимок слева), но не в других режимах (правый снимок экрана):

![Сравнение режимов Teams](media/teams-mode-comparison.png)

Кроме того, в других режимах присутствие самообнаправления недоступно, как показано здесь.

![Снимок экрана: самообнахождение на первом собрании](media/meetings-first-no-self-presence-general.png)
 
**Примечание.** 
 <sup>1</sup> В настоящее время SfBwithTeamsCollab и SfBOnly работают одинаково, но цель состоит в том, чтобы режим SfBOnly также отключил функции каналов и файлов в Teams. Промежуточным решением является скрытие каналов с помощью политики разрешений приложений.


## <a name="impact-of-mode-on-other-policy-settings"></a>Влияние режима на другие параметры политики
Как описано выше, режим сосуществования влияет на функции, доступные в клиенте Teams пользователя. Это означает, что значение режима может иметь приоритет над значением других параметров политики в зависимости от режима. В частности, режим сосуществования влияет на то, будут ли соблюдаться следующие параметры политики:

|**Modality (App)**|**Policy.Setting**|
|---|---|
|Чат|TeamsMessagingPolicy.AllowUserChat|
|Звонки|TeamsCallingPolicy.AllowPrivateCalling|
|Планирование собраний|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Администраторам  не требуется явно настраивать эти параметры политики в режиме совместной работы, но важно понимать, что эти параметры правильно настроены в определенном режиме. 

|Режим|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly или Islands|Включено|Включено|Включено|Включено|
|SfBWithTeamsCollabAndMeetings|Отключено|Отключено|Включено|Включено|
|SfBWithTeamsCollab или SfBOnly|Отключено|Отключено|Отключено|Отключено|
||||||

При использовании PowerShell командлет проверяет конфигурацию соответствующих параметров `Grant-CsTeamsUpgradePolicy` в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy, чтобы определить, будут ли эти параметры переопределяться TeamsUpgradePolicy и, если да, в PowerShell выведется информационное сообщение.  Как было отмечено выше, больше не нужно настраивать эти другие параметры политики. Ниже приводится пример того, как выглядит предупреждение PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Статьи по теме

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




