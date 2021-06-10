---
title: Настройка телефонного подтверждения для пользователей на собрании в Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как настроить Teams, чтобы запросить подтверждение звонка, чтобы системы голосовой почты не могли подключаться к собраниям, если вызываемая связь не может ответить на звонок.
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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="def6c-103">Настройка подтверждения телефонного и телефонного набора для пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="def6c-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="def6c-104">Звонки на собрание и звонки на мой номер — очень полезные способы пригласить участников присоединиться к собранию, а существующим — присоединиться к собранию с помощью обычного или мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="def6c-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="def6c-105">Однако если вызываемая связь не может ответить на звонок и на звонок отвечает система голосовой почты, система голосовой почты подключена к собранию, и участники смогут слушать ее, пока она не будет удалена из собрания.</span><span class="sxs-lookup"><span data-stu-id="def6c-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="def6c-106">Чтобы системы голосовой почты не могли подключаться к собраниям при звонках на телефонный номер и вызываемая связь не может ответить на звонок, вы можете настроить Teams, чтобы запросить подтверждение подключения к собранию от вызываемого человека.</span><span class="sxs-lookup"><span data-stu-id="def6c-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="def6c-107">Если вызываемая связь не может ответить на звонок и на звонок отвечает система голосовой почты, система голосовой почты не будет подключена к собранию, так как не будет предоставлять подтверждение для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="def6c-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="def6c-108">Если эта возможность включена, люди, которые получают звонок или звонок на мой номер, должны подтвердить, что они хотят присоединиться к собранию, нажав 1 на традиционном или мобильном телефоне.</span><span class="sxs-lookup"><span data-stu-id="def6c-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="def6c-109">Чтобы включить эту возможность для всех собраний в организации, задайте для параметра ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) параметр ```true``` .</span><span class="sxs-lookup"><span data-stu-id="def6c-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="def6c-110">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="def6c-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="def6c-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="def6c-111">Related topics</span></span>

- [<span data-ttu-id="def6c-112">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="def6c-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="def6c-113">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="def6c-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)