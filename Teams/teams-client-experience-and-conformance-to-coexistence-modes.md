---
title: Взаимодействие с клиентом Teams и соответствие режимам сосуществования
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Узнайте о взаимодействию с клиентами Teams и совместимости с режимами сосуществования (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903364"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Взаимодействие с клиентом Teams и соответствие режимам сосуществования

<a name="about-upgrade-basic"></a>

Цель режимов сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) – это простой и предсказуемый опыт конечных пользователей в том, что в Организации переход с Skype для бизнеса на Teams.  Для Организации, перемещающейся в Teams, режим " **только для Teams** " является конечным пунктом для каждого пользователя, хотя не всем пользователям должны быть назначены **только команды** (или любой другой режим) одновременно.  Перед тем как пользователи приходили в режим TeamsOnly, организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями, которые не являются **участниками** , и тем, кто еще не в состоянии. 

Когда пользователь входит в любой из режимов Skype для бизнеса, все входящие разговоры и звонки перенаправляются клиенту Skype для бизнеса пользователя. Чтобы избежать путаницы и удостовериться в том, что функция маршрутизации, вызов и чат в клиенте Teams отключена, когда пользователь входит в любой из режимов Skype для бизнеса. Аналогичным образом планирование собраний в Teams явным образом отключается, если пользователи находятся в режимах SfBOnly или SfBWithTeamsCollab, и явно включаются, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.

Так как присутствие является индикатором доступности в чате и звонке, то при отключении чата и звонков в Teams также отображается самообнаружение в группах (то есть отображается собственное состояние присутствия в клиенте Teams на рисунке пользователя). 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Изменение доступных функциональных возможностей клиента Teams в зависимости от режима

Доступные функции в Teams зависят от режима сосуществования пользователя, который задается с помощью TeamsUpgradePolicy. В таблице ниже приведено краткое описание поведения.

|Эффективный режим пользователя|Взаимодействие с клиентом Teams|
|---|---|
|Любой режим Skype для бизнеса|Звонки, чат и самообнаружение отключены.|
|SfBWithTeamsCollabAndMeetings|Доступно планирование собраний|
|SfBWithTeamsCollab или SfBOnly<sup>1</sup>|Планирование собраний недоступно|
|||

На следующих снимках экрана показано различие между режимами " **только для Teams** ", " **острова** " и всеми другими режимами. Обратите внимание на то, что значки чата и вызова по умолчанию доступны только в режиме " **только для групп** " или " **острова** " (на рисунке слева), но не в других режимах (на снимке экрана справа):

![Параллельное сравнение режимов групп](media/teams-mode-comparison.png)

Кроме того, самообнаружение в других режимах недоступно, как показано здесь.

![Снимок экрана с самообнаружением для собраний в начале собрания](media/meetings-first-no-self-presence-general.png)
 
**Примечание.**
<sup>1</sup> в настоящее время поведение SfBwithTeamsCollab и SfBOnly работает одинаково, но для работы с файлами в Teams и в режиме SfBOnly также можно отключить каналы и файлы. В списке временные каналы можно скрыть с помощью политики разрешений приложений.


## <a name="impact-of-mode-on-other-policy-settings"></a>Влияние режима для других параметров политики
Как описано выше, режим сосуществования пользователя влияет на функциональные возможности, доступные в клиенте Teams в пользовательском интерфейсе. Это означает, что значение Mode может иметь приоритет над значением других параметров политики, в зависимости от режима. В частности, режим сосуществования влияет на то, выполняются ли следующие параметры политики.

|**Модальность (приложение)**|**Политика. параметр**|
|---|---|
|Чат|TeamsMessagingPolicy.AllowUserChat|
|Звонки|TeamsCallingPolicy.AllowPrivateCalling|
|Планирование собраний|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Администраторам *не* нужно явно задавать эти параметры политики при использовании режима совместного существования, но важно понимать, что эти параметры работают следующим образом для определенного режима. 

|Режиме|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly или острова|Включено|Включено|Включено|Включено|
|SfBWithTeamsCollabAndMeetings|Отключено|Отключено|Включено|Включено|
|SfBWithTeamsCollab или SfBOnly|Отключено|Отключено|Отключено|Отключено|
||||||

При использовании PowerShell `Grant-CsTeamsUpgradePolicy` командлет проверяет конфигурацию соответствующих параметров в TeamsMessagingPolicy, TeamsCallingPolicy и TeamsMeetingPolicy, чтобы определить, будут ли эти параметры заменены TeamsUpgradePolicy, и если да, то в PowerShell будет выдано информационное сообщение.  Как указано выше, больше не нужно настраивать эти параметры политики. Ниже показано, как выглядит предупреждение PowerShell.

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Статьи по теме

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




