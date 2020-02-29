---
title: Настройка удаленного доступа для собрания — подтверждение для пользователей в Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как настроить команды для запроса подтверждения исходящих вызовов, чтобы предотвратить подключение систем голосовой почты к собраниям, если вызывающий абонент не может ответить на звонок.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339481"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Настройка подтверждения исходящих подключений к собранию для пользователей в Microsoft Teams

Звонить и звонить мне – это очень полезные способы пригласить участников присоединиться к собранию и присоединиться к собранию с помощью обычного или мобильного телефона. Тем не менее, если абонент не может ответить на звонок, и на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию, и участники смогут прослушать его, пока он не будет удален из собрания.

Чтобы предотвратить подключение систем голосовой почты к собраниям, когда исходящий набор отправляется на номер телефона, и вызывающий абонент не может ответить на него, вы можете настроить в Teams запрос на подтверждение для абонента, чтобы присоединиться к собранию. Если абонент не может ответить на звонок, и на звонок отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как она не будет содержать подтверждения для присоединения.

Если эта возможность включена, пользователи, принимающие звонок или звонок мне, должны подтвердить, что они хотят присоединиться к собранию, нажав 1 на своем традиционном или мобильном телефоне.

Чтобы включить эту возможность для всех собраний в вашей организации, установите ```EnableDialOutJoinConfirmation``` параметр командлета [Set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) ```true```. Для этого выполните следующую команду:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Статьи по теме

- [Настройка функции "Позвонить мне" для пользователей](set-up-the-call-me-feature-for-your-users.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)