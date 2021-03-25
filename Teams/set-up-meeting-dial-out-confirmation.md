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
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117097"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="9fcb4-103">Подтверждение о том, что собрание настроено для пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9fcb4-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="9fcb4-104">Звонки на собрания и звонки на мой номер — это очень полезный способ пригласить участников присоединиться к собранию, а существующим — присоединиться к собранию с помощью традиционной или мобильной связи.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="9fcb4-105">Однако если вызываемая связь не может ответить на звонок, а на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию, и участники смогут прослушивать его, пока не будет удалено из собрания.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="9fcb4-106">Чтобы системы голосовой почты не могли подключаться к собраниям при звонках на номер телефона вызываемого человека, который не может ответить на звонок, вы можете настроить Teams для запроса подтверждения от вызываемого человека, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="9fcb4-107">Если звонок не может ответить на звонок, а звонок отвечает системой голосовой почты, система голосовой почты не будет подключена к собранию, так как не будет предоставлять подтверждение для подключений.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="9fcb4-108">Если эта возможность включена, люди, которые получают звонок на мой номер или звонок на мой номер, должны подтвердить свое участие в собрании, нажав 1 на традиционном или мобильном телефоне.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="9fcb4-109">Чтобы включить эту возможность для всех собраний в организации, задайте для параметра ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) параметр ```true``` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="9fcb4-110">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9fcb4-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="9fcb4-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9fcb4-111">Related topics</span></span>

- [<span data-ttu-id="9fcb4-112">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="9fcb4-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="9fcb4-113">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="9fcb4-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)