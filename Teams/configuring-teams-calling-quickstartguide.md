---
title: 'Краткое руководство по началу работы: Настройка планов звонков'
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
description: Краткое руководство по настройке планов звонков в Microsoft Teams, чтобы можно было получить доступ к группе пользователей и работать с ними.
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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="76a86-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76a86-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="76a86-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="76a86-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="76a86-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="76a86-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="76a86-106">Мы рекомендуем использовать в этом руководстве по быстрому запуску, что вы прочитали [телефонную систему с тарифными планами](calling-plan-landing-page.md) и [FastTrack](https://aka.ms/cloudvoice) , чтобы спланировать и устранить успешный выпуск.</span><span class="sxs-lookup"><span data-stu-id="76a86-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="76a86-107">Добавляя планы звонков — компоненты Microsoft 365 и Office 365 на платформе Skype для бизнеса — теперь вы можете использовать Teams для совершения и приема телефонных звонков на стационарные и мобильные телефоны через коммутируемую телефонную сеть общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="76a86-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Снимок экрана, на котором показана страница "Контакты" в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="76a86-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="76a86-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="76a86-110">Чтобы включить на вкладке " **звонки** " в разделе "Пользователи Teams" поддержку вызова 1:1 в Teams и использование клиента Teams, поддерживающего вызов 1:1 Teams.</span><span class="sxs-lookup"><span data-stu-id="76a86-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="76a86-111">Чтобы научиться управлять вызовом 1:1 в Teams, прочтите [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="76a86-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="76a86-112">Чтобы получить информацию о том, какие клиенты поддерживают вызов, ознакомьтесь с разделом [ограничения и спецификации для Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="76a86-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="76a86-113">В настоящее время Голосовая почта будет недоступна на вкладке "звонки", если только пользователь не поддерживает звонки по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="76a86-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="76a86-114">Предварительные требования для включения **панели набора номера** в Teams</span><span class="sxs-lookup"><span data-stu-id="76a86-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="76a86-115">Чтобы включить и использовать в Teams вкладку для **набора номера** , вы должны будете подготавливать пользователей для звонков на телефонную систему и планы звонков.</span><span class="sxs-lookup"><span data-stu-id="76a86-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="76a86-116">Сведения о том, как настроить планы звонков, читайте в статье [Настройка планов звонков](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="76a86-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="76a86-117">Кроме того, только для пользователей Teams необходимо убедиться в том, что в политике вызова Teams включена поддержка закрытого вызова.</span><span class="sxs-lookup"><span data-stu-id="76a86-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="76a86-118">Дополнительные сведения [можно найти в разделе Управление группами на переходе в новый центр администрирования Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) .</span><span class="sxs-lookup"><span data-stu-id="76a86-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="76a86-119">Вы также можете использовать прямую маршрутизацию, чтобы предоставить пользователям возможность звонить и принимать звонки по КТСОП.</span><span class="sxs-lookup"><span data-stu-id="76a86-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="76a86-120">Чтобы научиться настраивать прямую переадресацию, прочтите параметр [настроить прямую маршрутизацию](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="76a86-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="76a86-121">Использование TeamsUpgradePolicy для управления тем, где наземный Звонок</span><span class="sxs-lookup"><span data-stu-id="76a86-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="76a86-122">Чтобы указать, будут ли входящие звонки (и разговоры) на землю в Teams или Skype для бизнеса, администраторы используют TeamsUpgradePolicy, используя либо [центр администрирования Microsoft Teams](https://aka.ms/teamsadmincenter) , либо удаленный сеанс Windows PowerShell с помощью командлетов [Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype) .</span><span class="sxs-lookup"><span data-stu-id="76a86-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="76a86-123">Настройка по умолчанию TeamsUpgradePolicy — это режим "острова", который предназначен для того, чтобы гарантировать, что существующие бизнес-процессы не прерываются при развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="76a86-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="76a86-124">По умолчанию звонки по протоколу VoIP, КТСОП и Федеративные пользователи по-прежнему будут перенаправляться в Skype для бизнеса, пока вы не обновите политику, чтобы включить входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="76a86-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="76a86-125">Если получатели находятся в режиме острова, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="76a86-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="76a86-126">Входящие звонки VOIP, поступающие в Skype для бизнеса, всегда размещаются в клиенте Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="76a86-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="76a86-127">Входящие звонки VOIP, созданные в Teams Land в Teams, *если отправитель и получатель находятся в одном и том же клиенте*.</span><span class="sxs-lookup"><span data-stu-id="76a86-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="76a86-128">Входящий федеративных VOIP (вне зависимости от того, какой клиент является источником) и PSTN-звонки всегда поступают в клиенте Skype для бизнеса получателя.</span><span class="sxs-lookup"><span data-stu-id="76a86-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="76a86-129">Чтобы гарантировать, что входящие звонки VOIP и PSTN всегда помещаются в клиенте Teams пользователя, обновите режим сосуществования пользователя, чтобы он был TeamsOnly (то есть назначьте ему экземпляр "UpgradeToTeams" TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="76a86-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="76a86-130">Более подробную информацию о режимах сосуществования и TeamsUpgradePolicy можно найти в [статье Руководство по миграции и взаимодействию для организаций, использующих команды совместно со Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="76a86-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="76a86-131">**Пуск**</span><span class="sxs-lookup"><span data-stu-id="76a86-131">**NOTES**</span></span>
 - <span data-ttu-id="76a86-132">IP-телефоны Skype для бизнеса будут получать звонки, даже если пользователь находится в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="76a86-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="76a86-133">Пользователи, которым были предоставлены лицензии на телефонную систему и планы звонков для использования в Skype для бизнеса Online (например, им назначено значение OnlineVoiceRoutingPolicy), будут использовать вкладку звонки в Teams и смогут разгрузить исходящие звонки PSTN из Teams без участия администратора.</span><span class="sxs-lookup"><span data-stu-id="76a86-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="76a86-134">Настройка пользователей для получения входящих звонков по протоколу VOIP и КТСОП в Teams</span><span class="sxs-lookup"><span data-stu-id="76a86-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="76a86-135">Чтобы убедиться в том, что пользователи получат все входящие звонки по протоколу VOIP и PSTN в Teams, установите для пользователя режим сосуществования TeamsOnly в центре администрирования Microsoft Teams или воспользуйтесь удаленным сеансом Windows PowerShell в Skype для бизнеса, чтобы обновить TeamsUpgradePolicy следующим образом.</span><span class="sxs-lookup"><span data-stu-id="76a86-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="76a86-136">См. также</span><span class="sxs-lookup"><span data-stu-id="76a86-136">See also</span></span>
[<span data-ttu-id="76a86-137">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="76a86-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="76a86-138">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="76a86-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="76a86-139">Телефонная система с планами звонков</span><span class="sxs-lookup"><span data-stu-id="76a86-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="76a86-140">Справочник по командлетам PowerShell в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="76a86-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

