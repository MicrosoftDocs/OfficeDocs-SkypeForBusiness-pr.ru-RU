---
title: Настройка подтверждения набора номера для пользователей в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как настроить Teams для запроса подтверждения исходящего подключения, чтобы системы голосовой почты не могли подключаться к собраниям, если вызываемый пользователь не может ответить на звонок.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271564"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Настройка подтверждения телефонного доступа к собранию для пользователей в Microsoft Teams

Исходящие звонки на собрание и звонки по телефону — это полезные способы пригласить участников присоединиться к собранию и присоединиться к собранию с помощью традиционного или мобильного телефона. Однако если вызываемый человек не может ответить на звонок, а на звонок отвечает система голосовой почты, система голосовой почты подключается к собранию. Участники смогут прослушивать его, пока он не будет удален из собрания.

Чтобы системы голосовой почты не могли подключаться к собраниям, когда на номер телефона отправляется телефонный звонок и вызываемый пользователь не может ответить на звонок, можно настроить Teams, чтобы запросить подтверждение от вызываемого пользователя для присоединения к собранию. Если вызываемый человек не может ответить на звонок, а на звонок отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как не предоставит подтверждение для присоединения к собранию.

Если эта возможность включена, пользователи, получающие звонок или звонок по телефону, должны подтвердить, что хотят присоединиться к собранию, нажав 1 на традиционном или мобильном телефоне или произнеся "ОК". Подтверждение не позволит пользователю присоединиться к собранию с помощью голосовой почты.

Чтобы включить эту возможность для всех собраний в организации, ```EnableDialOutJoinConfirmation``` задайте для параметра [командлета Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) значение ```true```. Чтобы задать этот параметр, выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Статьи по теме

- [Настройка функции "Позвонить мне" для пользователей](set-up-the-call-me-feature-for-your-users.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
