---
title: Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Краткое руководство по настройке планов звонков в Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc1c20f87103dc91a317e58dac03389275b255f2
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694699"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="71585-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71585-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="71585-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="71585-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="71585-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="71585-106">Чтобы спланировать и успешно провести развертывание, помимо этого краткого руководства рекомендуем также использовать [практическое руководство](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) и [FastTrack](https://aka.ms/cloudvoice).</span><span class="sxs-lookup"><span data-stu-id="71585-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="71585-107">За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="71585-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Звонки в Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="71585-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="71585-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="71585-110">Включение вкладки **звонки** в группах пользователи должны иметь 1:1 вызов включено в группах и с помощью команды клиента, вызов команд 1:1.</span><span class="sxs-lookup"><span data-stu-id="71585-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="71585-111">Чтобы узнать, как управлять 1:1 вызов в группах, прочитайте [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="71585-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="71585-112">Чтобы узнать, какие клиенты поддерживают вызова, ознакомьтесь с [ограничения и характеристики для групп Майкрософт](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="71585-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="71585-113">На данный момент голосовой почты не будут доступны в вкладке звонки, если пользователь включен для вызовов ТСОП.</span><span class="sxs-lookup"><span data-stu-id="71585-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="71585-114">Необходимые условия для включения панель **Набора номера** в группах</span><span class="sxs-lookup"><span data-stu-id="71585-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="71585-115">Для включения вкладки **Панели набора номера** в группах и разрешить пользователям выполнение и прием звонков ТСОП необходимо будет к подготовке пользователей для телефонной системой и вызов планов.</span><span class="sxs-lookup"><span data-stu-id="71585-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="71585-116">Чтобы узнать, как настраивать вызове планы, прочитайте [Set up вызов планы](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="71585-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="71585-117">Разрешить пользователям mand и принимать звонки по ТСОП можно также использовать прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="71585-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="71585-118">Чтобы узнать, как настроить прямой маршрутизации, прочитайте [Настройка прямой маршрутизации](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="71585-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="71585-119">Настройка политики взаимодействия Teams</span><span class="sxs-lookup"><span data-stu-id="71585-119">Teams interop policy configuration</span></span>
<span data-ttu-id="71585-120">Для включения групп начать принимать звонки, вам потребуется обновить команды обновления и политики группы взаимодействия, с помощью [групп Майкрософт & Скайп по центру администрирования бизнеса](https://aka.ms/teamsadmincenter) или с помощью удаленного сеанса Windows PowerShell с Скайп для бизнеса [ `*-CsTeamsUpgradePolicy`и `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) командлеты, можно настроить переадресацию звонков для группы.</span><span class="sxs-lookup"><span data-stu-id="71585-120">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="71585-121">Дополнительные сведения о политике обновления группы и политики взаимодействия команды можно [миграции и руководство по взаимодействию для организаций, с помощью команды Скайп для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="71585-121">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="71585-122">Чтобы найти командлеты PowerShell, необходимую, введите «CsTeamsUpgradePolicy» или «CsTeamsInteropPolicy» в поле **Фильтр** в [Скайп документация командлета Business PowerShell](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="71585-122">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="71585-123">Значение по умолчанию групп политики обновления и взаимодействия</span><span class="sxs-lookup"><span data-stu-id="71585-123">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="71585-124">Конфигурация политики по умолчанию в Teams предназначена для обеспечения непрерывности бизнес-процессов в ходе развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-124">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="71585-125">По умолчанию звонки по VoIP, ТСОП и федеративные звонки вашим пользователям будут по-прежнему поступать в Skype для бизнеса до тех пор, пока вы не обновите политику и не активируете входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-125">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="71585-126">Это гарантирует отсутствие непредвиденных нарушений в работе служб голосовой связи при пилотном запуске и развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-126">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="71585-127">Команды обновления политики по умолчанию будет храниться в унаследованный режим, который будет поддерживать групп взаимодействия политику, чтобы определить, где чаты и вызовы маршрутизирует--группы или Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71585-127">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="71585-128">Поведение группы обновление политики и скоро будет изменения политики взаимодействия команды, как описано в [руководстве по взаимодействию для организаций, с помощью команды Скайп для бизнеса и миграции](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="71585-128">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="71585-129">В политике взаимодействия Teams задана следующая конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71585-129">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="71585-130">В конфигурации по умолчанию действует следующее поведение.</span><span class="sxs-lookup"><span data-stu-id="71585-130">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="71585-131">**Для существующих клиентов Skype для бизнеса** эта политика будет направлять все звонки Skype для бизнеса в Skype для бизнеса, а звонки Teams — в Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-131">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="71585-132">Когда действует эта политика, звонки по ТСОП и федеративные звонки буду направляться в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71585-132">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="71585-133">**Для клиентов без Skype для бизнеса** в Teams помимо звонков между пользователями Teams будут доступны только исходящие звонки по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="71585-133">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="71585-134">Чтобы принимать в Teams звонки по ТСОП, измените политику взаимодействия Teams, назначенную пользователям.</span><span class="sxs-lookup"><span data-stu-id="71585-134">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="71585-135">Пользователи, которым были назначены лицензии на службу телефонной системы с планами звонков, предназначенные для использования со Skype для бизнеса Online, и у которых настроена глобальная политика взаимодействия Teams по умолчанию, получат доступ к вкладке "Звонки" в Teams и смогут совершать исходящие звонки по ТСОП из Teams без необходимости каких-либо действий со стороны администраторов.</span><span class="sxs-lookup"><span data-stu-id="71585-135">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="71585-136">Настройка Teams для приема входящих звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="71585-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="71585-137">Получать входящие вызовы ТСОП в группах, необходимо настроить группы по умолчанию, вызов приложения с применением команды обновления политики с соответствующей группы взаимодействия политики, которая задает `CallingDefaultClient` параметр группам.</span><span class="sxs-lookup"><span data-stu-id="71585-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71585-138">Эту конфигурацию рекомендуется применить к стартовому набору пользователей, чтобы они могли опробовать новые потрясающие возможности звонков в Teams, прежде чем вносить изменения на более широком уровне или на уровне всей организации.</span><span class="sxs-lookup"><span data-stu-id="71585-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="71585-139">Для продолжения использования устаревших групп политики обновления, воспользоваться следующие предварительно настроенного политики взаимодействия групп для маршрутизации входящих звонков ТСОП к группам:</span><span class="sxs-lookup"><span data-stu-id="71585-139">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="71585-140">Если выбрано использование обновленного обновления политики групп, им необходимо назначить TeamsOnly режима для пользователей.</span><span class="sxs-lookup"><span data-stu-id="71585-140">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="71585-141">Приведенная выше политика действует следующим образом.</span><span class="sxs-lookup"><span data-stu-id="71585-141">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="71585-142">**Для существующих клиентов Skype для бизнеса** эта политика будет перенаправлять входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-142">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="71585-143">В их число входят звонки по VoIP (из Teams и Skype для бизнеса) и звонки по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="71585-143">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="71585-144">**Для клиентов без Skype для бизнеса** звонки по ТСОП будут поступать в Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="71585-145">В настоящее время задание параметру `CallingDefaultClient` значения "Teams" будет также влиять на звонки на IP-телефоны Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71585-145">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="71585-146">Входящие вызовы не будут поступать на эти телефоны. Их будут принимать только клиенты Teams.</span><span class="sxs-lookup"><span data-stu-id="71585-146">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="71585-147">Обратитесь к [365 стратегия Майкрософт](https://aka.ms/O365Roadmap) для получения сведений о поддержке для существующего сертифицированного телефонов SIP.</span><span class="sxs-lookup"><span data-stu-id="71585-147">Please consult the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="71585-148">Как настроить пользователям пользоваться PSTN вызывает в группах</span><span class="sxs-lookup"><span data-stu-id="71585-148">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="71585-149">При использовании устаревшего обновления политики групп, применение политики взаимодействия команды, как описано выше, с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell можно настроить переадресацию звонков для группы:</span><span class="sxs-lookup"><span data-stu-id="71585-149">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="71585-150">Если вы решите использовать режим TeamsOnly, можно изменить режим сосуществования пользователя TeamsOnly, путем группами Майкрософт & Скайп по центру администрирования бизнеса, или с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell можно настроить переадресацию звонков для группы:</span><span class="sxs-lookup"><span data-stu-id="71585-150">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="71585-151">См. также</span><span class="sxs-lookup"><span data-stu-id="71585-151">See also</span></span>
[<span data-ttu-id="71585-152">Set up Calling Plans (Настройка планов звонков)</span><span class="sxs-lookup"><span data-stu-id="71585-152">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="71585-153">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="71585-153">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="71585-154">Практическое руководство по телефонной системе с планами звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71585-154">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="71585-155">Справочник по командлетам PowerShell для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="71585-155">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="71585-156">Справочник по командлетам PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="71585-156">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
