---
title: Настройка подтверждения телефонного и телефонного набора для пользователей в Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как настроить Teams, чтобы запросить подтверждение звонка, чтобы системы голосовой почты не могли подключаться к собраниям, если вызываемая связь не может ответить на звонок.
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 121a4cbd4527f4724f9868a83ab70dd75fb9b327
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865518"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Настройка подтверждения для пользователей в качестве телефонного номера в Microsoft Teams

Звонки на собрание и звонки на мой номер — очень полезные способы пригласить участников присоединиться к собранию, а существующим — присоединиться к собранию с помощью обычного или мобильного телефона. Однако если вызываемая связь не может ответить на звонок и на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию, и участники смогут слушать ее, пока она не будет удалена из собрания.

Чтобы системы голосовой почты не могли подключаться к собраниям при звонках на телефонный номер и вызываемая связь не может ответить на звонок, вы можете настроить Teams, чтобы запросить подтверждение подключения к собранию от вызываемого человека. Если вызываемая связь не может ответить на звонок и на звонок отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как не будет предоставлять подтверждение для подключения к собранию.

Если эта возможность включена, люди, которые получают звонок или звонок на мой номер, должны подтвердить, что они хотят присоединиться к собранию, нажав 1 на традиционном или мобильном телефоне.

Чтобы включить эту возможность для всех собраний в организации, задайте для параметра ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) параметр ```true``` . Для этого выполните следующую команду:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Статьи по теме

- [Настройка функции "Позвонить мне" для пользователей](set-up-the-call-me-feature-for-your-users.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)