---
title: Настройка телефонного подтверждения для пользователей на собрании в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
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
ms.openlocfilehash: 9db8d3882ea7d05b1bc3600682c0c803040b4c10
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055659"
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
