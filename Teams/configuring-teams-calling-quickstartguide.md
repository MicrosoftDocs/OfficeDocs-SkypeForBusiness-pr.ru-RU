---
title: "Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Краткое руководство по настройке планов звонков в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bf2aa9b698516882ed5e48b4d9b7b639b74af40e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="db55e-103">Краткое руководство по началу работы. Настройка планов звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db55e-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="db55e-104">Это руководство поможет вам подготовить группу пользователей для испытания возможностей планов звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="db55e-105">Ознакомьтесь с объявлением о планах звонков в Teams от 12 декабря 2017 г.: [Intelligent Communications takes the next step with calling in Teams (Звонки в Teams как новый этап интеллектуальных коммуникаций)](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="db55e-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="db55e-106">Чтобы спланировать и успешно провести развертывание, помимо этого краткого руководства рекомендуем также использовать [практическое руководство](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) и [FastTrack](https://aka.ms/cloudvoice).</span><span class="sxs-lookup"><span data-stu-id="db55e-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="db55e-107">За счет добавления планов звонков (компонента Office 365 на основе Skype для бизнеса) приложение Teams теперь позволяет делать и принимать звонки на стационарные и мобильные телефоны по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="db55e-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Звонки в Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="db55e-109">Что необходимо для активации вкладки **Звонки** в Teams</span><span class="sxs-lookup"><span data-stu-id="db55e-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="db55e-110">Чтобы включить вкладку **Звонки** в Teams и позволить пользователям совершать и принимать звонки по ТСОП, необходимо подготовить пользователей для использования службы телефонной системы и планов звонков.</span><span class="sxs-lookup"><span data-stu-id="db55e-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="db55e-111">Соответствующие инструкции см. в разделе [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0) (Настройка планов звонков).</span><span class="sxs-lookup"><span data-stu-id="db55e-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db55e-112">Перед настройкой планов звонков в Teams ознакомьтесь с приведенными далее ограничениями.</span><span class="sxs-lookup"><span data-stu-id="db55e-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="db55e-113">**Teams не поддерживает гибридную голосовую связь.** Гибридная голосовая связь в Teams сейчас не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="db55e-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="db55e-114">Клиентам, использующим гибридную голосовую связь, не рекомендуется изменять какие-либо политики для получения звонков в Teams, так как это приведет к нарушению работы службы.</span><span class="sxs-lookup"><span data-stu-id="db55e-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="db55e-115">**Teams не поддерживает федеративные звонки.** Федеративные звонки (звонки между клиентами или компаниями) сейчас не поддерживаются в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="db55e-116">Пока их поддержка не будет реализована, такие звонки всегда будут перенаправляться в Skype для бизнеса вне зависимости от того, как настроены вызовы.</span><span class="sxs-lookup"><span data-stu-id="db55e-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="db55e-117">Настройка политики взаимодействия Teams</span><span class="sxs-lookup"><span data-stu-id="db55e-117">Teams interop policy configuration</span></span>
<span data-ttu-id="db55e-118">Чтобы активировать возможность приема звонков в Teams, необходимо перенастроить политику взаимодействия Teams на перенаправление звонков в это приложение. Используйте для этого удаленный сеанс Windows PowerShell с командлетами для Skype для бизнеса [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="db55e-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="db55e-119">Дополнительные сведения о политике взаимодействия Teams см. в разделе [Взаимодействие Microsoft Teams и Skype для бизнеса](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span><span class="sxs-lookup"><span data-stu-id="db55e-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="db55e-120">Чтобы найти нужные командлеты PowerShell, введите "CsTeamsInteropPolicy" в поле **Фильтр** в [документации по командлетам PowerShell в Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="db55e-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="db55e-121">Политика взаимодействия Teams по умолчанию</span><span class="sxs-lookup"><span data-stu-id="db55e-121">Default Teams interop policy</span></span>
<span data-ttu-id="db55e-122">Конфигурация политики по умолчанию в Teams предназначена для обеспечения непрерывности бизнес-процессов в ходе развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="db55e-123">По умолчанию звонки по VoIP, ТСОП и федеративные звонки вашим пользователям будут по-прежнему поступать в Skype для бизнеса до тех пор, пока вы не обновите политику и не активируете входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="db55e-124">Это гарантирует отсутствие непредвиденных нарушений в работе служб голосовой связи при пилотном запуске и развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="db55e-125">В политике взаимодействия Teams задана следующая конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db55e-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="db55e-126">В конфигурации по умолчанию действует следующее поведение.</span><span class="sxs-lookup"><span data-stu-id="db55e-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="db55e-127">**Для существующих клиентов Skype для бизнеса** эта политика будет направлять все звонки Skype для бизнеса в Skype для бизнеса, а звонки Teams — в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="db55e-128">Когда действует эта политика, звонки по ТСОП и федеративные звонки буду направляться в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db55e-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="db55e-129">**Для клиентов без Skype для бизнеса** в Teams помимо звонков между пользователями Teams будут доступны только исходящие звонки по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="db55e-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="db55e-130">Чтобы принимать в Teams звонки по ТСОП, измените политику взаимодействия Teams, назначенную пользователям.</span><span class="sxs-lookup"><span data-stu-id="db55e-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="db55e-131">Пользователи, которым были назначены лицензии на службу телефонной системы с планами звонков, предназначенные для использования со Skype для бизнеса Online, и у которых настроена глобальная политика взаимодействия Teams по умолчанию, получат доступ к вкладке "Звонки" в Teams и смогут совершать исходящие звонки по ТСОП из Teams без необходимости каких-либо действий со стороны администраторов.</span><span class="sxs-lookup"><span data-stu-id="db55e-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="db55e-132">Настройка Teams для использования политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="db55e-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="db55e-133">Глобальная политика взаимодействия Teams по умолчанию применяется ко всем пользователям в клиенте и настраивается с параметрами по умолчанию, описанными выше.</span><span class="sxs-lookup"><span data-stu-id="db55e-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="db55e-134">Если по какой-либо причине вы предоставили пользователям разные политики и хотели бы вернуться к настройкам по умолчанию, вам нужно применить глобальную политику взаимодействия Teams через удаленный сеанс Windows PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db55e-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="db55e-135">Хотя вы можете изменить значения глобальной политики взаимодействия Teams по умолчанию, настоятельно не рекомендуем это делать.</span><span class="sxs-lookup"><span data-stu-id="db55e-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="db55e-136">Настройка Teams для приема входящих звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="db55e-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="db55e-137">Для приема входящих звонков по ТСОП в Teams потребуется настроить Teams как приложение для звонков по умолчанию, применив политику взаимодействия Teams с параметром `CallingDefaultClient`, имеющим значение "Teams".</span><span class="sxs-lookup"><span data-stu-id="db55e-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db55e-138">Эту конфигурацию рекомендуется применить к стартовому набору пользователей, чтобы они могли опробовать новые потрясающие возможности звонков в Teams, прежде чем вносить изменения на более широком уровне или на уровне всей организации.</span><span class="sxs-lookup"><span data-stu-id="db55e-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="db55e-139">Для направления входящих звонков по ТСОП в Teams рекомендуем рассмотреть возможность использования следующей готовой политики взаимодействия Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="db55e-140">Приведенная выше политика действует следующим образом.</span><span class="sxs-lookup"><span data-stu-id="db55e-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="db55e-141">**Для существующих клиентов Skype для бизнеса** эта политика будет перенаправлять входящие звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="db55e-142">В их число входят звонки по VoIP (из Teams и Skype для бизнеса) и звонки по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="db55e-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="db55e-143">Федеративные звонки будут по-прежнему поступать в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db55e-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="db55e-144">**Для клиентов без Skype для бизнеса** звонки по ТСОП будут поступать в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="db55e-145">Федеративные звонки в Teams сейчас **не поддерживаются**.</span><span class="sxs-lookup"><span data-stu-id="db55e-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="db55e-146">В настоящее время задание параметру `CallingDefaultClient` значения "Teams" будет также влиять на звонки на IP-телефоны Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db55e-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="db55e-147">Входящие вызовы не будут поступать на эти телефоны. Их будут принимать только клиенты Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="db55e-148">Сведения о поддержке существующих сертифицированных SIP-телефонов см. в документе с [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) (Переход со Skype для бизнеса на Microsoft Teams: стратегия внедрения возможностей).</span><span class="sxs-lookup"><span data-stu-id="db55e-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="db55e-149">Настройка Teams для приема звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="db55e-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="db55e-150">Примените политику взаимодействия Teams как описано выше через удаленный сеанс Windows PowerShell для Skype для бизнеса, чтобы перенаправлять звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="db55e-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="db55e-151">Настройка Teams для разрешения пользователям изменять предпочитаемый способ звонков</span><span class="sxs-lookup"><span data-stu-id="db55e-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="db55e-152">Чтобы пользователи могли самостоятельно выбирать предпочитаемый способ приема вызовов, т. е. решать, принимать ли звонки в Teams или Skype для бизнеса, создайте настраиваемую политику взаимодействия Teams, которая активирует параметр `AllowEndUserClientOverride`.</span><span class="sxs-lookup"><span data-stu-id="db55e-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="db55e-153">Далее приведен пример политики взаимодействия Teams, которая предоставляет пользователю возможность выбора подходящего способа работы со звонками.</span><span class="sxs-lookup"><span data-stu-id="db55e-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="db55e-154">После применения настраиваемой политики к пользователям в клиенте Teams им станет доступна возможность самостоятельно изменять предпочитаемое приложение для звонков.</span><span class="sxs-lookup"><span data-stu-id="db55e-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![Предпочитаемое приложение для звонков](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="db55e-156">Эту конфигурацию рекомендуется применить к стартовому набору пользователей, прежде чем вносить изменения на более широком уровне или на уровне всей организации.</span><span class="sxs-lookup"><span data-stu-id="db55e-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="db55e-157">Создание и применение настраиваемой политики взаимодействия Teams</span><span class="sxs-lookup"><span data-stu-id="db55e-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="db55e-158">Чтобы создать, как описано выше, настраиваемую политику взаимодействия Teams в ходе удаленного сеанса Windows PowerShell для Skype для бизнеса, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="db55e-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="db55e-159">См. также</span><span class="sxs-lookup"><span data-stu-id="db55e-159">See also</span></span>
[<span data-ttu-id="db55e-160">Set up Calling Plans (Настройка планов звонков)</span><span class="sxs-lookup"><span data-stu-id="db55e-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="db55e-161">Взаимодействие Microsoft Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="db55e-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="db55e-162">Практическое руководство по телефонной системе с планами звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db55e-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="db55e-163">Справочник по командлетам PowerShell для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="db55e-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="db55e-164">Справочник по командлетам PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="db55e-164">PowerShell cmdlet reference for Teams</span></span>](https://docs.microsoft.com/powershell/module/teams)
