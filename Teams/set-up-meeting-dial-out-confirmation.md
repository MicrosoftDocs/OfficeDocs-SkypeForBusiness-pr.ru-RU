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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="4bfe6-103">Настройка подтверждения исходящих подключений к собранию для пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4bfe6-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="4bfe6-104">Звонить и звонить мне – это очень полезные способы пригласить участников присоединиться к собранию и присоединиться к собранию с помощью обычного или мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="4bfe6-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="4bfe6-105">Тем не менее, если абонент не может ответить на звонок, и на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию, и участники смогут прослушать его, пока он не будет удален из собрания.</span><span class="sxs-lookup"><span data-stu-id="4bfe6-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="4bfe6-106">Чтобы предотвратить подключение систем голосовой почты к собраниям, когда исходящий набор отправляется на номер телефона, и вызывающий абонент не может ответить на него, вы можете настроить в Teams запрос на подтверждение для абонента, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="4bfe6-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="4bfe6-107">Если абонент не может ответить на звонок, и на звонок отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как она не будет содержать подтверждения для присоединения.</span><span class="sxs-lookup"><span data-stu-id="4bfe6-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="4bfe6-108">Если эта возможность включена, пользователи, принимающие звонок или звонок мне, должны подтвердить, что они хотят присоединиться к собранию, нажав 1 на своем традиционном или мобильном телефоне.</span><span class="sxs-lookup"><span data-stu-id="4bfe6-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="4bfe6-109">Чтобы включить эту возможность для всех собраний в вашей организации, установите ```EnableDialOutJoinConfirmation``` параметр командлета [Set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) ```true```.</span><span class="sxs-lookup"><span data-stu-id="4bfe6-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="4bfe6-110">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4bfe6-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="4bfe6-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4bfe6-111">Related topics</span></span>

- [<span data-ttu-id="4bfe6-112">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="4bfe6-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="4bfe6-113">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="4bfe6-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)