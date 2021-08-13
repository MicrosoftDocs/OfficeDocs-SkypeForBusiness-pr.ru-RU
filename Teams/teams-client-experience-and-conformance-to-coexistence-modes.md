---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Узнайте о Teams и соответствии режимам совместной работы (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: e49e8d7fd76bb3ecb14ad1c3d19142fbca28f978144578f42e5d106ef7c1d511
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321251"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Взаимодействие с клиентом Teams и соответствие режимам сосуществования

<a name="about-upgrade-basic"></a>

Режимы сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) обеспечивают простой и предсказуемый опыт для конечных пользователей по мере перехода организаций с Skype для бизнеса на Teams.  Для организации, перемещаемой в  Teams, режим "только Teams" является конечным пунктом назначения для  каждого пользователя, хотя не все пользователи должны быть назначены только Teams (или любой другой режим) одновременно.  До выхода пользователей в режим TeamsOnly организации могут использовать любой из режимов Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые работают только Teams, и теми, кто еще не используется.  

Когда пользователь находится в любом из режимов Skype для бизнеса, все входящие чаты и звонки перенанаются его Skype для бизнеса клиенту. Чтобы избежать путаницы с конечными пользователями и обеспечить правильную маршрутику, вызовы и чаты в клиенте Teams отключены, когда пользователь Skype для бизнеса режиме. Аналогично, планирование собраний в Teams явным образом отключено, если пользователи находятся в режиме SfBOnly или SfBWithTeamsCollab и явно включены, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.

Так как присутствие указывает на доступность в чате и звонках, когда чат и вызовы отключены, в Teams (т. е. отображение собственного присутствия в клиенте Teams на фотографии пользователя) также скрыто. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Изменение доступных функций Teams клиента в зависимости от режима

Доступные в Teams функции зависят от режима совместной работы пользователя, установленного командой TeamsUpgradePolicy. В следующей таблице кратко поведению:

|Режим эффективности пользователя|Опыт работы в Teams клиента|
|---|---|
|Любой Skype для бизнеса режиме|Вызовы, чат и самосовершенная беседа отключаются.|
|SfBWithTeamsCollabAndMeetings|Доступно планирование собраний|
|SfBWithTeamsCollab или SfBOnly<sup>1</sup>|Планирование собраний недоступно|
|||

На снимках экрана ниже показано, чем отличается режим Teams **или** "Только **на** островах" и всеми другими режимами. Обратите внимание на то, что значки чата и  звонков по умолчанию доступны в режиме Teams **Или** Только на островах (снимок слева), но не в других режимах (снимок справа):

![Сравнение режимов Teams рядом](media/teams-mode-comparison.png)

Кроме того, в других режимах самообнаправление недоступно, как показано ниже.

![Снимок экрана: самосовершенная присутствие в первом собрании](media/meetings-first-no-self-presence-general.png)
 
**Примечание.** 
 <sup>1.</sup> В настоящее время SfBwithTeamsCollab и SfBOnly ведут себя одинаково, но в режиме SfBOnly необходимо также отключить функции channels и Files в Teams. Тем временем каналы могут быть скрыты с помощью политики разрешений приложений.


## <a name="impact-of-mode-on-other-policy-settings"></a>Влияние режима на другие параметры политики
Как было описано выше, режим совместной работы влияет на функции, доступные в клиенте Teams пользователя. Это означает, что значение режима может иметь приоритет над значением других параметров политики в зависимости от режима. В частности, режим сосуществования влияет на то, будут ли соблюдаться следующие параметры политики:

|**Modality (App)**|**Policy.Setting**|
|---|---|
|Чат|TeamsMessagingPolicy.AllowUserChat|
|Звонки|TeamsCallingPolicy.AllowPrivateCalling|
|Планирование собраний|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

*Администраторам не нужно* явно настраивать эти параметры политики при использовании режима совместной работы, но важно понимать, что эти параметры правильно настроены в определенном режиме. 

|Режим|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly или Islands|Включено|Включено|Включено|Включено|
|SfBWithTeamsCollabAndMeetings|Отключено|Отключено|Включено|Включено|
|SfBWithTeamsCollab или SfBOnly|Отключено|Отключено|Отключено|Отключено|
||||||

При использовании PowerShell командлет проверяет конфигурацию соответствующих параметров `Grant-CsTeamsUpgradePolicy` в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy, чтобы определить, будут ли эти параметры подменимы TeamsUpgradePolicy и, если да, в PowerShell выведется информационное сообщение.  Как было отмечено выше, больше не нужно настраивать другие параметры политики. Вот как выглядит предупреждение PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Статьи по теме

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](./migration-interop-guidance-for-teams-with-skype.md)