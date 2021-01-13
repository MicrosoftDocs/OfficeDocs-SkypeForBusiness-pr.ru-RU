---
title: Настройка подтверждения телефонного набора для пользователей в Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как настроить Teams для запроса подтверждения звонка, чтобы системы голосовой почты не могли подключаться к собраниям, когда вызываемая связь не может ответить на звонок.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806149"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Подтверждение о том, что собрание настроено для пользователей в Microsoft Teams

Звонки на собрания и звонки на мой номер — это очень полезный способ пригласить участников присоединиться к собранию, а существующим — присоединиться к собранию с помощью традиционной или мобильной связи. Однако если вызываемая связь не может ответить на звонок, а на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию, и участники смогут прослушивать его, пока не будет удалено из собрания.

Чтобы системы голосовой почты не могли подключаться к собраниям при звонках на номер телефона вызываемого человека, который не может ответить на звонок, вы можете настроить Teams для запроса подтверждения от вызываемого человека, чтобы он присоединился к собранию. Если вызываемая почта не может ответить на звонок и на него отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как не будет предоставлять подтверждение для подключений к собранию.

Если эта возможность включена, люди, которые получают звонок на мой номер или звонок на мой номер, должны подтвердить свое участие в собрании, нажав 1 на традиционном или мобильном телефоне.

Чтобы включить эту возможность для всех собраний в организации, задайте для параметра ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) параметр ```true``` . Для этого выполните следующую команду:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Статьи по теме

- [Настройка функции "Позвонить мне" для пользователей](set-up-the-call-me-feature-for-your-users.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)