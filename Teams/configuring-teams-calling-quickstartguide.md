---
title: Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: Rowille, lolaj
search.appverid: MET150
description: Краткое руководство по настройке планов звонков в Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6c719d17938986ff6568b73864bc131667e4e7
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401985"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="b4184-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4184-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="b4184-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="b4184-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="b4184-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="b4184-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="b4184-106">Рекомендуется, параллельно с краткое руководство прочитать [Телефонной системы с помощью вызова планы](calling-plan-landing-page.md) и [она](https://aka.ms/cloudvoice) плану и диск успешного развертывания.</span><span class="sxs-lookup"><span data-stu-id="b4184-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="b4184-107">За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="b4184-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Звонки в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="b4184-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="b4184-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="b4184-110">Включение вкладки **звонки** в группах пользователи должны иметь 1:1 вызов включено в группах и с помощью команды клиента, вызов команд 1:1.</span><span class="sxs-lookup"><span data-stu-id="b4184-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="b4184-111">Чтобы узнать, как управлять 1:1 вызов в группах, прочитайте [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b4184-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="b4184-112">Чтобы узнать, какие клиенты поддерживают вызова, ознакомьтесь с [ограничения и характеристики для групп Майкрософт](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="b4184-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="b4184-113">На данный момент голосовой почты не будут доступны в вкладке звонки, если пользователь включен для вызовов ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b4184-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="b4184-114">Необходимые условия для включения панель **Набора номера** в группах</span><span class="sxs-lookup"><span data-stu-id="b4184-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="b4184-115">Для включения вкладки **Панели набора номера** в группах и разрешить пользователям выполнение и прием звонков ТСОП необходимо будет к подготовке пользователей для телефонной системой и вызов планов.</span><span class="sxs-lookup"><span data-stu-id="b4184-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="b4184-116">Чтобы узнать, как настраивать вызове планы, прочитайте [Set up вызов планы](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="b4184-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="b4184-117">Можно также использовать прямой маршрутизации, чтобы разрешить пользователям выполнение и прием звонков ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b4184-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="b4184-118">Чтобы узнать, как настроить прямой маршрутизации, прочитайте [Настройка прямой маршрутизации](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="b4184-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="b4184-119">Использование TeamsUpgradePolicy для элемента управления, где land звонки</span><span class="sxs-lookup"><span data-stu-id="b4184-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="b4184-120">Чтобы управлять ли входящие звонки (и беседы) land в группы или Скайп для бизнеса, Администраторы используют TeamsUpgradePolicy, с помощью любого из [групп Майкрософт центра администрирования](https://aka.ms/teamsadmincenter) или с помощью удаленного сеанса Windows PowerShell с [Скайп для бизнеса](https://docs.microsoft.com/powershell/module/skype) командлеты.</span><span class="sxs-lookup"><span data-stu-id="b4184-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="b4184-121">Конфигурация по умолчанию TeamsUpgradePolicy является острова режим, в котором разработан для обеспечения, существующего бизнес-рабочие процессы не прерывается во время развертывания групп.</span><span class="sxs-lookup"><span data-stu-id="b4184-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="b4184-122">По умолчанию VoIP, ТСОП и федеративных вызовов для пользователей будет направляться в Скайп для бизнеса до обновления политики, включающей входящих звонков для группы.</span><span class="sxs-lookup"><span data-stu-id="b4184-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="b4184-123">Когда получатели находятся в режиме о-ва:</span><span class="sxs-lookup"><span data-stu-id="b4184-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="b4184-124">Входящие VOIP вызывает этот происхождение в Скайп Business всегда Земля в Скайп получателя для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="b4184-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="b4184-125">Входящие VOIP вызывает, которая была создана в land группами в группах, *Если отправитель и получатель, тому же владельцу*.</span><span class="sxs-lookup"><span data-stu-id="b4184-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="b4184-126">Входящая федеративных VOIP, (независимо от того, какой компьютер исходит) и вызовы PSTN всегда Земля в Скайп получателя для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="b4184-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="b4184-127">Чтобы гарантировать, что входящие VOIP и PSTN вызывает всегда Земля в группы клиента, обновите режиме сосуществования пользователя быть TeamsOnly (это значит, назначить их экземпляр TeamsUpgradePolicy «UpgradeToTeams».</span><span class="sxs-lookup"><span data-stu-id="b4184-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="b4184-128">Дополнительные сведения о режимах сосуществования и TeamsUpgradePolicy можно [миграции и руководство по взаимодействию для организаций, с помощью команды Скайп для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="b4184-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="b4184-129">**ПРИМЕЧАНИЯ**</span><span class="sxs-lookup"><span data-stu-id="b4184-129">**NOTES**</span></span>
 - <span data-ttu-id="b4184-130">Скайп для бизнеса IP-телефонов будет принимать звонки, даже в том случае, если пользователь находится в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b4184-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="b4184-131">Пользователи, которые были созданы с телефонной системой и вызов планов лицензии для использования с Скайп для бизнеса в Интернет (например назначенные им значение OnlineVoiceRoutingPolicy), будут иметь вкладке звонков включен в группах и вводятся исходящие вызовы ТСОП из Группы без необходимости никаких административных действий Администраторы.</span><span class="sxs-lookup"><span data-stu-id="b4184-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="b4184-132">Как настроить пользователям принимать все входящие VOIP и PSTN вызывает в группах</span><span class="sxs-lookup"><span data-stu-id="b4184-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="b4184-133">Чтобы убедиться, что пользователи получают все входящие звонки VOIP и ТСОП в группах, нужно выбрать режим пользователя сосуществования TeamsOnly в центре администрирования группами Майкрософт, или использовать Скайп для бизнеса удаленного сеанса Windows PowerShell для обновления TeamsUpgradePolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b4184-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="b4184-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b4184-134">See also</span></span>
[<span data-ttu-id="b4184-135">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="b4184-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="b4184-136">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b4184-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="b4184-137">Система телефон с Тарифные планы</span><span class="sxs-lookup"><span data-stu-id="b4184-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="b4184-138">Скайп для Справочник командлетов PowerShell бизнеса</span><span class="sxs-lookup"><span data-stu-id="b4184-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

