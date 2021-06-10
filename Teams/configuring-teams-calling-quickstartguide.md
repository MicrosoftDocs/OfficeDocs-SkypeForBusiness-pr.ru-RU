---
title: Краткое руководство по настройке планов звонков
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Краткое руководство по настройке планов звонков Microsoft Teams для настройки набора пользователей.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101185"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="e3c1b-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e3c1b-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="e3c1b-104">Это руководство поможет вам настроить набор пользователей, чтобы они могли изучить планы звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="e3c1b-105">Ознакомьтесь с объявлением о планах звонков от 12 декабря 2017 г. в [Teams.](https://aka.ms/ipyqus) Интеллектуальные коммуникации: следующий шаг — звонок в Teams</span><span class="sxs-lookup"><span data-stu-id="e3c1b-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="e3c1b-106">Мы рекомендуем параллельно с этим кратким руководством [](calling-plan-landing-page.md) ознакомиться с телефонная система с планами звонков и [FastTrack,](https://aka.ms/cloudvoice) чтобы спланировать и добиться успешного раздатки.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="e3c1b-107">Добавив планы звонков Microsoft 365 и Office 365 с помощью Skype для бизнеса, вы сможете использовать Teams для телефонных звонков на мобильные и на мобильные телефоны и на мобильные телефоны через телефонную сеть общего пользования (ПСN).</span><span class="sxs-lookup"><span data-stu-id="e3c1b-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Снимок экрана: страница "Контакты" в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="e3c1b-109">Необходимые условия для включения **вкладки Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="e3c1b-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="e3c1b-110">Чтобы включить **вкладку** Звонки в Teams, пользователям необходимо включить в Teams звонков 1:1 и использовать клиент Teams, который поддерживает Teams звонков 1:1.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="e3c1b-111">Чтобы узнать, как управлять звонками 1:1 в Teams, ознакомьтесь со статьей [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e3c1b-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="e3c1b-112">Чтобы узнать, какие клиенты поддерживают вызовы, ознакомьтесь со статьей Ограничения [и спецификации для](./limits-specifications-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e3c1b-113">В настоящее время голосовая почта недоступна на вкладке Звонки, если только пользователь не включен для звонков по ННР.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="e3c1b-114">Необходимые условия для включения панели **набора** номера в Teams</span><span class="sxs-lookup"><span data-stu-id="e3c1b-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="e3c1b-115">Чтобы включить **вкладку Панель** набора номера в Teams и разрешить пользователям звонить и принимать звонки по ЗВОНКОВ по ЗВОНКОВ, необходимо телефонная система и планы звонков.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="e3c1b-116">Чтобы узнать, как настроить планы звонков, ознакомьтесь со статьей [Настройка планов звонков.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="e3c1b-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="e3c1b-117">Кроме того, Teams только для пользователей, убедитесь, что в политике Teams звонков включена Teams звонков.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="e3c1b-118">Дополнительные [сведения см. в Teams](./manage-teams-skypeforbusiness-admin-center.md) управления переходом на новую Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="e3c1b-119">Вы также можете использовать прямую маршрутику, чтобы разрешить пользователям звонить и принимать звонки по ННР.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="e3c1b-120">Чтобы узнать, как настроить прямую маршрутику, ознакомьтесь со ссылкой [Настройка прямой маршрутии.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e3c1b-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="e3c1b-121">Использование TeamsUpgradePolicy для управления местом звонков</span><span class="sxs-lookup"><span data-stu-id="e3c1b-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="e3c1b-122">Для управления входящие звонки (и чаты) в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя Центр администрирования [Microsoft Teams](https://aka.ms/teamsadmincenter) или удаленный [](/powershell/module/skype) сеанс Windows PowerShell с командлетами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="e3c1b-123">По умолчанию TeamsUpgradePolicy имеет вид Islands, который гарантирует, что существующие бизнес-процессы не будут прерываться во время Teams развертывания.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="e3c1b-124">По умолчанию voIP, STN и федеражные звонки пользователям будут перенаправлены на Skype для бизнеса до тех пор, пока вы не обновите политику, чтобы включить входящие звонки Teams.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="e3c1b-125">Когда получатели находятся в режиме островов:</span><span class="sxs-lookup"><span data-stu-id="e3c1b-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="e3c1b-126">Входящие вызовы VOIP, Skype для бизнеса всегда перенаправ в клиент Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="e3c1b-127">Входящие вызовы VOIP, Teams в Teams, если отправитель и получение находятся *в одном клиенте.*</span><span class="sxs-lookup"><span data-stu-id="e3c1b-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="e3c1b-128">Входящие федератированные вызовы VOIP (независимо от того, какой клиент задается) и вызовы по ДНР всегда будут поступать в Skype для бизнеса клиента Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="e3c1b-129">Чтобы обеспечить постоянное перенастройку входящих вызовов VOIP и ПСПУ в клиенте Teams пользователя, обновите его режим совместной работы с TeamsOnly (то есть назначьте ему экземпляр UpgradeToTeams teamsUpgradePolicy).</span><span class="sxs-lookup"><span data-stu-id="e3c1b-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="e3c1b-130">Дополнительные сведения о режимах совместной работы и TeamsUpgradePolicy см. в руководстве по миграции и совместной Teams и [Skype для бизнеса](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="e3c1b-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="e3c1b-131">**Заметки**</span><span class="sxs-lookup"><span data-stu-id="e3c1b-131">**NOTES**</span></span>
 - <span data-ttu-id="e3c1b-132">Skype для бизнеса IP-телефоны будут принимать звонки, даже если пользователь находится в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="e3c1b-133">У пользователей, которые имеют лицензии на телефонная система и планы звонков для использования с Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), в Teams будет включена вкладка Вызовы, и они смогут звонить через Teams, не принимая никаких административных действий.</span><span class="sxs-lookup"><span data-stu-id="e3c1b-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="e3c1b-134">Настройка того, как настроить прием всех входящих звонков по voIP и STN в Teams</span><span class="sxs-lookup"><span data-stu-id="e3c1b-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="e3c1b-135">Чтобы гарантировать, что пользователи будут получать все входящие звонки voIP и STN в Teams, задайте для них режим сосуществования в TeamsOnly в Центре администрирования Microsoft Teams или используйте сеанс Skype для бизнеса удаленного Windows PowerShell для обновления TeamsUpgradePolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e3c1b-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="e3c1b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e3c1b-136">See also</span></span>
[<span data-ttu-id="e3c1b-137">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="e3c1b-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="e3c1b-138">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e3c1b-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="e3c1b-139">Телефонная система с тарифными планами</span><span class="sxs-lookup"><span data-stu-id="e3c1b-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="e3c1b-140">Skype для бизнеса Справочник по cmdhell PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3c1b-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)