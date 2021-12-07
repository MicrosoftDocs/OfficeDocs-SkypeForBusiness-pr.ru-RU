---
title: Настройка телефонного подтверждения для пользователей на собрании в Microsoft Teams
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
ms.openlocfilehash: ae670cec7adcca3dada49a3dcda0ae11f3d1b7b7
ms.sourcegitcommit: 70bba31b0ca4615a3c6a90f42d3568450ea51b82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2021
ms.locfileid: "61327257"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Настройка подтверждения телефонного набора для пользователей в Microsoft Teams

Звонки на собрание и звонки на мой номер — это полезные способы пригласить участников присоединиться к собранию, а существующим — присоединиться к собранию с помощью обычного или мобильного телефона. Однако если вызываемая почта не может ответить на звонок и на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию. Участники смогут слушать ее, пока она не будет удалена из собрания.

Чтобы системы голосовой почты не могли подключаться к собраниям при звонках на телефонный номер и вызываемая связь не может ответить на звонок, вы можете настроить Teams, чтобы запросить подтверждение от вызываемого человека, чтобы он присоединился к собранию. Если вызываемая связь не может ответить на звонок и на звонок отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как не будет предоставлять подтверждение для подключения к собранию.

Если эта возможность включена, люди, которые получают звонок или звонок на мой номер, должны подтвердить, что они хотят присоединиться к собранию, нажав 1 на традиционном или мобильном телефоне или нажав "ОК".

Чтобы включить эту возможность для всех собраний в организации, задайте для параметра ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) параметр ```true``` . Чтобы установить этот параметр, запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Статьи по теме

- [Настройка функции "Позвонить мне" для пользователей](set-up-the-call-me-feature-for-your-users.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
