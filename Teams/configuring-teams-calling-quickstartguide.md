---
title: 'Краткое руководство: настройка планов звонков'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Краткое руководство по настройке планов звонков в Microsoft Teams для настройки набора пользователей.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eed9ec99445c2f632f1443343b7076aadfbb70a8
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739047"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="2761c-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2761c-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="2761c-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="2761c-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="2761c-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="2761c-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="2761c-106">Рекомендуем параллельно с этим кратким руководством прочитать [](calling-plan-landing-page.md) телефонную систему с планами звонков и [fastTrack,](https://aka.ms/cloudvoice) чтобы спланировать успешный разкат.</span><span class="sxs-lookup"><span data-stu-id="2761c-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="2761c-107">Добавив планы звонков — функции Microsoft 365 и Office 365, которые работают на платформе Skype для бизнеса, — теперь вы можете использовать Teams для телефонных звонков на мобильные и на мобильные и на мобильные телефоны или на мобильные телефоны по телефонной сети общего пользования (ПС).</span><span class="sxs-lookup"><span data-stu-id="2761c-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Снимок экрана: страница "Контакты" в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="2761c-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="2761c-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="2761c-110">Чтобы включить вкладку **"Звонки"** в Teams, пользователям необходимо включить 1:1 звонки в Teams и использовать клиент Teams, который поддерживает звонков в Teams 1:1.</span><span class="sxs-lookup"><span data-stu-id="2761c-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="2761c-111">Чтобы узнать, как управлять вызовами 1:1 в Teams, ознакомьтесь с [командой Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2761c-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="2761c-112">Чтобы узнать, какие клиенты поддерживают вызовы, ознакомьтесь с ограничениями и [спецификациями Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)</span><span class="sxs-lookup"><span data-stu-id="2761c-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="2761c-113">В настоящее время голосовая почта на вкладке "Звонки" недоступна, если только для пользователя не включена возможность звонков по ННР.</span><span class="sxs-lookup"><span data-stu-id="2761c-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="2761c-114">Необходимые условия для включения панели **набора номера** в Teams</span><span class="sxs-lookup"><span data-stu-id="2761c-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="2761c-115">Чтобы включить **вкладку "Панель** набора номера" в Teams и разрешить пользователям делать и принимать звонки по ТЕЛЕФОННОЙ СЕТИ, необходимо обу числеть пользователей к телефонной системе и планам звонков.</span><span class="sxs-lookup"><span data-stu-id="2761c-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="2761c-116">Чтобы узнать, как настроить планы звонков, прочитайте [статью "Настройка планов звонков".](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="2761c-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="2761c-117">Кроме того, для пользователей Teams необходимо включить в политике звонков Teams разрешение личных звонков.</span><span class="sxs-lookup"><span data-stu-id="2761c-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="2761c-118">Дополнительные [сведения см. в центре](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) администрирования Microsoft Teams во время перехода на новый центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="2761c-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="2761c-119">Вы также можете использовать прямую маршрутику, чтобы разрешить пользователям делать и принимать звонки по ННР.</span><span class="sxs-lookup"><span data-stu-id="2761c-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="2761c-120">Чтобы узнать, как настроить прямую маршрутику, ознакомьтесь с тем, [как настроить прямую маршрутику.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)</span><span class="sxs-lookup"><span data-stu-id="2761c-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="2761c-121">Использование TeamsUpgradePolicy для управления участком звонков</span><span class="sxs-lookup"><span data-stu-id="2761c-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="2761c-122">Чтобы управлять тем, должны ли входящие звонки (и чаты) понищаться в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя центр администрирования [Microsoft Teams](https://aka.ms/teamsadmincenter) или удаленный Windows PowerShell с командлетами [Skype](https://docs.microsoft.com/powershell/module/skype) для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2761c-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="2761c-123">По умолчанию TeamsUpgradePolicy имеет режим Islands, который гарантирует, что существующие бизнес-процессы не будут прерываться во время развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="2761c-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="2761c-124">По умолчанию звонки по VoIP, ННР и федератный вызовы вашим пользователям будут продолжать маршрутироваться в Skype для бизнеса до тех пор, пока вы не обновите политику, чтобы включить входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="2761c-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="2761c-125">Если получатели находятся в режиме островов:</span><span class="sxs-lookup"><span data-stu-id="2761c-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="2761c-126">Входящие звонки VOIP, которые были произведены в Skype для бизнеса, всегда перенаправят в клиент Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="2761c-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="2761c-127">Входящие вызовы VOIP, которые были произведены в Teams, находятся в Teams, если отправитель и приемник находятся *в одном клиенте.*</span><span class="sxs-lookup"><span data-stu-id="2761c-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="2761c-128">Входящие федераированные вызовы VOIP (независимо от того, какой клиент из них поступает) и вызовы по ННР всегда перенаправят в клиент Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="2761c-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="2761c-129">Чтобы входящие вызовы VOIP и STN всегда были в клиенте Teams пользователя, обновите режим сосуществования пользователя на TeamsOnly (то есть назначьте ему экземпляр UpgradeToTeams) TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="2761c-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="2761c-130">Дополнительные сведения о режимах сосуществования и TeamsUpgradePolicy см. в руководстве по миграции и совместной работе организаций, использующих Teams вместе со [Skype для бизнеса.](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="2761c-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="2761c-131">**ПРИМЕЧАНИЯ**</span><span class="sxs-lookup"><span data-stu-id="2761c-131">**NOTES**</span></span>
 - <span data-ttu-id="2761c-132">IP-телефоны Skype для бизнеса будут принимать звонки, даже если пользователь находится в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2761c-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="2761c-133">Пользователи, имеющие лицензии на телефонную систему и планы звонков для использования со Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут иметь вкладку "Звонки" в Teams и могут принимать исходящие звонки по STN из Teams без административных действий администраторов.</span><span class="sxs-lookup"><span data-stu-id="2761c-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="2761c-134">Настройка пользователей для получения всех входящих вызовов VOIP и STN в Teams</span><span class="sxs-lookup"><span data-stu-id="2761c-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="2761c-135">Чтобы обеспечить прием пользователями всех входящих вызовов VOIP и STN в Teams, установите для пользователя режим сосуществования TeamsOnly в Центре администрирования Microsoft Teams или используйте удаленный Windows PowerShell Skype для бизнеса для обновления TeamsUpgradePolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2761c-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="2761c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="2761c-136">See also</span></span>
[<span data-ttu-id="2761c-137">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="2761c-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="2761c-138">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2761c-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="2761c-139">Телефонная система с тарифными планами</span><span class="sxs-lookup"><span data-stu-id="2761c-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="2761c-140">Справочник по с помощью cmdlet для Skype для бизнеса PowerShell</span><span class="sxs-lookup"><span data-stu-id="2761c-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

