---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Группы взаимодействия с пользователем и comformance режимы сосуществования
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4865d66d4d3ff1257d0fc4bd355a65c7c1330101
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934790"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Взаимодействие с клиентом Teams и соответствие режимам сосуществования

> [!NOTE]
> На этой странице описаны важно, недавно выпущенных изменения в поведение клиента групп, когда пользователи находятся в любой из Скайп для режимов Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


Совместная работа режимы предназначен для простой, прогнозируемый работы для конечных пользователей как организаций перехода от Скайп для бизнеса группам.  Для перемещения групп организации режим TeamsOnly — конечному получателю для каждого пользователя, хотя не все пользователи должны быть назначены TeamsOnly (или любой другой режим) в то же время.  Пользователей, достигает TeamsOnly режиме организации могут использовать любой из Скайп для бизнеса режимов (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), чтобы убедиться в прогнозируемый связи между пользователями, которые TeamsOnly и тех, кто еще не. 

Когда пользователь находится в любой из Скайп для режимов бизнеса, все входящие чаты и вызовы направляются Скайп пользователя для клиента Business. Чтобы избежать путаницы конечного пользователя и гарантировать правильную маршрутизацию, функциональные возможности телефонной и чата в клиенте группами отключена, если пользователь не во всех Скайп для режимов Business. Аналогично планирования собраний в группах явным образом отключается, когда пользователи находятся в режимах SfBOnly или SfBWithTeamsCollab и явно включены, если пользователь находится в режиме SfBWithTeamsCollabAndMeetings.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Как доступные функции в клиенте команд изменяется на основе режима
Доступные функции в dependes группами в режиме сосуществования пользователя, как набор с TeamsUpgradePolicy. В следующей таблице описано поведение:

|Эффективное режим пользователя|Опытом группы клиента|
|---|---|
|Любой Скайп для режима бизнеса|Вызов и чата<sup>1</sup> отключены.|
|SfBWithTeamsCollabAndMeetings|Доступно на собрания планирования|
|SfBWithTeamsCollab или SfBOnly<sup>2</sup>|Планирование на собрания не поддерживается|
|||

Следующие снимки экрана иллюстрируют различие между TeamsOnly или о-ва режим и другие режимы. Обратите внимание, что значки чата и вызова доступны с TeamsOnly или о-ва режим (слева снимок экрана), но не другие режимы (правом снимок экрана):

![Отображает режим сравнения групп](media/teams-mode-comparison.png)


 
**Примечания:**
<sup>1</sup> чата собрания по-прежнему доступны.

<sup>2</sup> сейчас SfBwithTeamsCollab и SfBOnly ведут себя одинаково, но цель состоит в том, для режима SfBOnly также отключить функцию каналы и файлы в группах; Тем не менее в данный момент нет параметра, обеспечивающий в группах, чтобы отключить эту функцию.


## <a name="impact-of-mode-on-other-policy-settings"></a>Влияние режима от других параметров политики
Как описано выше пользователя сосуществования режим воздействия функциональных возможностей доступна в клиент группы пользователя. Это означает, что значение режима имеют приоритет над значение другие параметры политики, в зависимости от режима. В частности режиме сосуществования влияет ли соблюдаются следующие параметры политики:

|**Модальность (приложение)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Звонки|TeamsCallingPolicy.AllowPrivateCalling|
|Планирование собрания|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Администраторы должны *не* явно задать параметры политики, когда использование режима совместная работа, но важно понимать, что эти параметры эффективно работать следующим образом для указанного режима. 

|Режим|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly или о-ва|Включено|Включено|Включено|Включено|
|SfBWithTeamsCollabAndMeetings|Отключено|Отключено|Включено|Включено|
|SfBWithTeamsCollab или SfBOnly|Отключено|Отключено|Отключено|Отключено|
||||||

В ближайшем будущем `Grant-CsTeamsUpgradePolicy` командлет проверит конфигурации соответствующие параметры в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy, чтобы определить, если эти параметры будут внесены TeamsUpgradePolicy и если да, Информационное сообщение предоставляется в PowerShell.  Как указано выше, больше не требуется задать параметры политики. Ниже приведен пример предупреждение PowerShell выглядит как:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Связанные разделы

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




