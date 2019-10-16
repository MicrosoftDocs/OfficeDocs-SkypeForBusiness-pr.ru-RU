---
title: Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Краткое руководство по настройке планов звонков в Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87670ea398150e4895f2d87ccc48f60aba2d1377
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516482"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="3aabe-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3aabe-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="3aabe-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="3aabe-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="3aabe-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="3aabe-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="3aabe-106">Мы рекомендуем использовать в этом руководстве по быстрому запуску, что вы прочитали [телефонную систему с тарифными планами](calling-plan-landing-page.md) и [FastTrack](https://aka.ms/cloudvoice) , чтобы спланировать и устранить успешный выпуск.</span><span class="sxs-lookup"><span data-stu-id="3aabe-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="3aabe-107">За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="3aabe-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Снимок экрана, на котором показана страница "Контакты" в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="3aabe-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="3aabe-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="3aabe-110">Чтобы включить на вкладке " **звонки** " в разделе "Пользователи Teams" поддержку вызова 1:1 в Teams и использование клиента Teams, поддерживающего вызов 1:1 Teams.</span><span class="sxs-lookup"><span data-stu-id="3aabe-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="3aabe-111">Чтобы научиться управлять вызовом 1:1 в Teams, прочтите [Set-кстеамскаллингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3aabe-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="3aabe-112">Чтобы получить информацию о том, какие клиенты поддерживают вызов, ознакомьтесь с разделом [ограничения и спецификации для Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="3aabe-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="3aabe-113">В настоящее время Голосовая почта будет недоступна на вкладке "звонки", если только пользователь не поддерживает звонки по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="3aabe-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="3aabe-114">Предварительные требования для включения **панели набора номера** в Teams</span><span class="sxs-lookup"><span data-stu-id="3aabe-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="3aabe-115">Чтобы включить и использовать в Teams вкладку для **набора номера** , вы должны будете подготавливать пользователей для звонков на телефонную систему и планы звонков.</span><span class="sxs-lookup"><span data-stu-id="3aabe-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="3aabe-116">Сведения о том, как настроить планы звонков, читайте в статье [Настройка планов звонков](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="3aabe-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="3aabe-117">Вы также можете использовать прямую маршрутизацию, чтобы предоставить пользователям возможность звонить и принимать звонки по КТСОП.</span><span class="sxs-lookup"><span data-stu-id="3aabe-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="3aabe-118">Чтобы научиться настраивать прямую переадресацию, прочтите параметр [настроить прямую маршрутизацию](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="3aabe-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="3aabe-119">Использование Теамсупградеполици для управления тем, где наземный Звонок</span><span class="sxs-lookup"><span data-stu-id="3aabe-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="3aabe-120">Для управления входящими звонками (и сеансами) в Teams или Skype для бизнеса администраторы используют Теамсупградеполици, используя либо [центр администрирования Microsoft Teams](https://aka.ms/teamsadmincenter) , либо удаленный сеанс Windows PowerShell с помощью [Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype) . Командлеты.</span><span class="sxs-lookup"><span data-stu-id="3aabe-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="3aabe-121">Настройка по умолчанию Теамсупградеполици — это режим "острова", который предназначен для того, чтобы гарантировать, что существующие бизнес-процессы не прерываются при развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="3aabe-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="3aabe-122">По умолчанию звонки по протоколу VoIP, КТСОП и Федеративные пользователи по-прежнему будут перенаправляться в Skype для бизнеса, пока вы не обновите политику, чтобы включить входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="3aabe-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="3aabe-123">Если получатели находятся в режиме острова, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3aabe-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="3aabe-124">Входящие звонки VOIP, поступающие в Skype для бизнеса, всегда размещаются в клиенте Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="3aabe-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="3aabe-125">Входящие звонки VOIP, созданные в Teams Land в Teams, *если отправитель и получатель находятся в одном и том же клиенте*.</span><span class="sxs-lookup"><span data-stu-id="3aabe-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="3aabe-126">Входящий федеративных VOIP (вне зависимости от того, какой клиент является источником) и PSTN-звонки всегда поступают в клиенте Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="3aabe-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="3aabe-127">Чтобы гарантировать, что входящие звонки VOIP и PSTN всегда помещаются в клиенте Teams пользователя, обновите режим сосуществования пользователя, чтобы он был Теамсонли (то есть назначьте ему экземпляр "Упградетотеамс" Теамсупградеполици.</span><span class="sxs-lookup"><span data-stu-id="3aabe-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="3aabe-128">Более подробную информацию о режимах сосуществования и Теамсупградеполици можно найти в [статье Руководство по миграции и взаимодействию для организаций, использующих команды совместно со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="3aabe-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="3aabe-129">**Пуск**</span><span class="sxs-lookup"><span data-stu-id="3aabe-129">**NOTES**</span></span>
 - <span data-ttu-id="3aabe-130">IP-телефоны Skype для бизнеса будут получать звонки, даже если пользователь находится в режиме Теамсонли.</span><span class="sxs-lookup"><span data-stu-id="3aabe-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="3aabe-131">Пользователи, которым были предоставлены лицензии на телефонную систему и планы звонков для использования в Skype для бизнеса Online (например, им назначено значение Онлиневоицераутингполици), будут включены вкладка звонки в Teams, и они могут помещать исходящие вызовы PSTN из Teams без участия администратора.</span><span class="sxs-lookup"><span data-stu-id="3aabe-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="3aabe-132">Настройка пользователей для получения входящих звонков по протоколу VOIP и КТСОП в Teams</span><span class="sxs-lookup"><span data-stu-id="3aabe-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="3aabe-133">Чтобы убедиться в том, что пользователи получат все входящие звонки по протоколу VOIP и PSTN в Teams, установите для пользователя режим сосуществования Теамсонли в центре администрирования Microsoft Teams или воспользуйтесь удаленным сеансом Windows PowerShell в Skype для бизнеса, чтобы обновить Теамсупградеполици следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3aabe-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="3aabe-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3aabe-134">See also</span></span>
[<span data-ttu-id="3aabe-135">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="3aabe-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="3aabe-136">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3aabe-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="3aabe-137">Телефонная система с планами звонков</span><span class="sxs-lookup"><span data-stu-id="3aabe-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="3aabe-138">Справочник по командлетам PowerShell в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3aabe-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

