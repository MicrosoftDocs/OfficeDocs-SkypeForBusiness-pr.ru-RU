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
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: eea3c6ed4084648877fd31b84bb9cdea26986565
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856101"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="dad48-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dad48-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="dad48-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="dad48-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="dad48-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="dad48-106">Чтобы спланировать и успешно провести развертывание, помимо этого краткого руководства рекомендуем также использовать [практическое руководство](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) и [FastTrack](https://aka.ms/cloudvoice).</span><span class="sxs-lookup"><span data-stu-id="dad48-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="dad48-107">За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="dad48-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Звонки в Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="dad48-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="dad48-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="dad48-110">Чтобы включить вкладку **Звонки** в Teams и позволить пользователям совершать и принимать звонки по ТСОП, необходимо подготовить пользователей для использования службы телефонной системы и планов звонков.</span><span class="sxs-lookup"><span data-stu-id="dad48-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="dad48-111">Соответствующие инструкции см. в разделе [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans) (Настройка планов звонков).</span><span class="sxs-lookup"><span data-stu-id="dad48-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="dad48-112">Настройка политики взаимодействия Teams</span><span class="sxs-lookup"><span data-stu-id="dad48-112">Teams interop policy configuration</span></span>
<span data-ttu-id="dad48-113">Для включения групп начать принимать звонки, вам потребуется обновить команды обновления и политики группы взаимодействия, с помощью [групп Майкрософт & Скайп по центру администрирования бизнеса](https://aka.ms/teamsadmincenter) или с помощью удаленного сеанса Windows PowerShell с Скайп для бизнеса [ `*-CsTeamsUpgradePolicy`и `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) командлеты, можно настроить переадресацию звонков для группы.</span><span class="sxs-lookup"><span data-stu-id="dad48-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="dad48-114">Дополнительные сведения о политике обновления группы и политики взаимодействия команды можно [миграции и руководство по взаимодействию для организаций, с помощью команды Скайп для бизнеса](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="dad48-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="dad48-115">Чтобы найти командлеты PowerShell, необходимую, введите «CsTeamsUpgradePolicy» или «CsTeamsInteropPolicy» в поле **Фильтр** в [Скайп документация командлета Business PowerShell](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="dad48-115">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="dad48-116">Значение по умолчанию групп политики обновления и взаимодействия</span><span class="sxs-lookup"><span data-stu-id="dad48-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="dad48-117">Конфигурация политики по умолчанию в Teams предназначена для обеспечения непрерывности бизнес-процессов в ходе развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="dad48-118">По умолчанию звонки по VoIP, ТСОП и федеративные звонки вашим пользователям будут по-прежнему поступать в Skype для бизнеса до тех пор, пока вы не обновите политику и не активируете входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="dad48-119">Это гарантирует отсутствие непредвиденных нарушений в работе служб голосовой связи при пилотном запуске и развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="dad48-120">Команды обновления политики по умолчанию будет храниться в унаследованный режим, который будет поддерживать групп взаимодействия политику, чтобы определить, где чаты и вызовы маршрутизирует--группы или Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dad48-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="dad48-121">Поведение группы обновление политики и скоро будет изменения политики взаимодействия команды, как описано в [руководстве по взаимодействию для организаций, с помощью команды Скайп для бизнеса и миграции](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="dad48-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="dad48-122">В политике взаимодействия Teams задана следующая конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dad48-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="dad48-123">В конфигурации по умолчанию действует следующее поведение.</span><span class="sxs-lookup"><span data-stu-id="dad48-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="dad48-124">**Для существующих клиентов Skype для бизнеса** эта политика будет направлять все звонки Skype для бизнеса в Skype для бизнеса, а звонки Teams — в Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="dad48-125">Когда действует эта политика, звонки по ТСОП и федеративные звонки буду направляться в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dad48-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="dad48-126">**Для клиентов без Skype для бизнеса** в Teams помимо звонков между пользователями Teams будут доступны только исходящие звонки по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="dad48-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="dad48-127">Чтобы принимать в Teams звонки по ТСОП, измените политику взаимодействия Teams, назначенную пользователям.</span><span class="sxs-lookup"><span data-stu-id="dad48-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="dad48-128">Пользователи, которым были назначены лицензии на службу телефонной системы с планами звонков, предназначенные для использования со Skype для бизнеса Online, и у которых настроена глобальная политика взаимодействия Teams по умолчанию, получат доступ к вкладке "Звонки" в Teams и смогут совершать исходящие звонки по ТСОП из Teams без необходимости каких-либо действий со стороны администраторов.</span><span class="sxs-lookup"><span data-stu-id="dad48-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="dad48-129">Настройка Teams для приема входящих звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="dad48-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="dad48-130">Получать входящие вызовы ТСОП в группах, необходимо настроить группы по умолчанию, вызов приложения с применением команды обновления политики с соответствующей группы взаимодействия политики, которая задает `CallingDefaultClient` параметр группам.</span><span class="sxs-lookup"><span data-stu-id="dad48-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dad48-131">Эту конфигурацию рекомендуется применить к стартовому набору пользователей, чтобы они могли опробовать новые потрясающие возможности звонков в Teams, прежде чем вносить изменения на более широком уровне или на уровне всей организации.</span><span class="sxs-lookup"><span data-stu-id="dad48-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="dad48-132">Для продолжения использования устаревших групп политики обновления, воспользоваться следующие предварительно настроенного политики взаимодействия групп для маршрутизации входящих звонков ТСОП к группам:</span><span class="sxs-lookup"><span data-stu-id="dad48-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="dad48-133">Если выбрано использование обновленного обновления политики групп, им необходимо назначить TeamsOnly режима для пользователей.</span><span class="sxs-lookup"><span data-stu-id="dad48-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="dad48-134">Приведенная выше политика действует следующим образом.</span><span class="sxs-lookup"><span data-stu-id="dad48-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="dad48-135">**Для существующих клиентов Skype для бизнеса** эта политика будет перенаправлять входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="dad48-136">В их число входят звонки по VoIP (из Teams и Skype для бизнеса) и звонки по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="dad48-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="dad48-137">**Для клиентов без Skype для бизнеса** звонки по ТСОП будут поступать в Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="dad48-138">В настоящее время задание параметру `CallingDefaultClient` значения "Teams" будет также влиять на звонки на IP-телефоны Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dad48-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="dad48-139">Входящие вызовы не будут поступать на эти телефоны. Их будут принимать только клиенты Teams.</span><span class="sxs-lookup"><span data-stu-id="dad48-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="dad48-140">Сведения о поддержке существующих сертифицированных SIP-телефонов см. в документе с [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) (Переход со Skype для бизнеса на Microsoft Teams: стратегия внедрения возможностей).</span><span class="sxs-lookup"><span data-stu-id="dad48-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="dad48-141">Как настроить пользователям пользоваться PSTN вызывает в группах</span><span class="sxs-lookup"><span data-stu-id="dad48-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="dad48-142">При использовании устаревшего обновления политики групп, применение политики взаимодействия команды, как описано выше, с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell можно настроить переадресацию звонков для группы:</span><span class="sxs-lookup"><span data-stu-id="dad48-142">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="dad48-143">Если вы решите использовать режим TeamsOnly, может изменить режим сосуществования пользователя на TeamsOnly путем группами Майкрософт & Скайп по центру администрирования бизнеса, или с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell можно настроить переадресацию звонков для группы.</span><span class="sxs-lookup"><span data-stu-id="dad48-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="dad48-144">См. также</span><span class="sxs-lookup"><span data-stu-id="dad48-144">See also</span></span>
[<span data-ttu-id="dad48-145">Set up Calling Plans (Настройка планов звонков)</span><span class="sxs-lookup"><span data-stu-id="dad48-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="dad48-146">Руководство по миграции и взаимодействия для организаций, с помощью команды Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dad48-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="dad48-147">Практическое руководство по телефонной системе с планами звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dad48-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="dad48-148">Справочник по командлетам PowerShell для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dad48-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="dad48-149">Справочник по командлетам PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="dad48-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
