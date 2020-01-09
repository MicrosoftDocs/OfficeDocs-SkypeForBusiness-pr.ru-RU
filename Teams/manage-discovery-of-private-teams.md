---
title: Управление обнаружением закрытых команд в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как управлять возможностью обнаружения конфиденциальных команд пользователями Microsoft Teams с помощью предложений в галерее группы и в результатах поиска.
ms.openlocfilehash: e2e0ec956b40ff5e84bb29874c0dc567edefd034
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992014"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="849e3-103">Управление обнаружением закрытых команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="849e3-103">Manage discovery of private teams in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="849e3-104">Администраторы и владельцы групп могут определять, могут ли быть обнаружены частные команды для пользователей Microsoft Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="849e3-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="849e3-105">Если частная группа является обнаруживаемой, она отображается в результатах поиска и включается в предложения коллекции групп наряду с общедоступными группами в Teams.</span><span class="sxs-lookup"><span data-stu-id="849e3-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="849e3-106">Благодаря этому пользователи смогут легко находить и находить закрытые группы, к которым они хотят присоединиться.</span><span class="sxs-lookup"><span data-stu-id="849e3-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="849e3-107">Пользователи могут попросить присоединиться к закрытой команде, а владелец команды может утвердить или отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="849e3-107">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="849e3-108">Общие сведения об общедоступных группах, частных командах и обнаружении в Teams</span><span class="sxs-lookup"><span data-stu-id="849e3-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="849e3-109">Большинство организаций обладают следующими видами команд: общедоступные группы, обнаруживаемые закрытые команды и закрытые группы, не обнаруживаемые.</span><span class="sxs-lookup"><span data-stu-id="849e3-109">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Снимок экрана с коллекцией групп](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="849e3-111">Общедоступные группы</span><span class="sxs-lookup"><span data-stu-id="849e3-111">Public teams</span></span>

<span data-ttu-id="849e3-112">Общедоступные команды доступны для всех пользователей в вашей организации, чтобы присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="849e3-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="849e3-113">Общедоступные команды видны всем пользователям в коллекции Teams, и пользователи могут присоединиться к общедоступной команде, не требуя утверждения от владельца группы.</span><span class="sxs-lookup"><span data-stu-id="849e3-113">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="849e3-114">Примеры общедоступных команд включают в себя группу, в которой рассказывается о технологиях, группе для получения отзывов о ваших продуктах и команде для людей, карпулинг работать.</span><span class="sxs-lookup"><span data-stu-id="849e3-114">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="849e3-115">Обнаруживаемые закрытые группы</span><span class="sxs-lookup"><span data-stu-id="849e3-115">Discoverable private teams</span></span>

<span data-ttu-id="849e3-116">Обнаруживаемые закрытые команды могут быть присоединены, только когда владелец группы добавляет в них пользователей.</span><span class="sxs-lookup"><span data-stu-id="849e3-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="849e3-117">Если вы сделаете личную команду обнаруживаемой, она будет включена в список предложенных команд и результатов поиска в коллекции Teams.</span><span class="sxs-lookup"><span data-stu-id="849e3-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="849e3-118">Используйте обнаруживаемые закрытые команды для проектов и групп в Организации, где все знают, и где доступ к беседам и файлам в команде нужно контролировать.</span><span class="sxs-lookup"><span data-stu-id="849e3-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="849e3-119">Примеры: группа для отдела кадров, группа для всех руководителей в Организации и группа для руководителя и их непосредственных отчетов.</span><span class="sxs-lookup"><span data-stu-id="849e3-119">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="849e3-120">Не обнаруживаемые закрытые группы</span><span class="sxs-lookup"><span data-stu-id="849e3-120">Non-discoverable private teams</span></span>

<span data-ttu-id="849e3-121">Необнаруживаемые закрытые команды могут быть присоединены, только когда владелец группы добавляет в них пользователей.</span><span class="sxs-lookup"><span data-stu-id="849e3-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="849e3-122">Если вы сделаете закрытую команду необнаруживаемой, она будет скрыта от списка предлагаемых групп и удалена из результатов поиска в коллекции Teams.</span><span class="sxs-lookup"><span data-stu-id="849e3-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="849e3-123">Использование необнаруживаемых команд для совместной работы с конфиденциальными и весьма конфиденциальными разделами.</span><span class="sxs-lookup"><span data-stu-id="849e3-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="849e3-124">Примеры включают в себя команду для обсуждения предстоящего приобретения и команды обсудить изменения в стратегическом направлении Организации.</span><span class="sxs-lookup"><span data-stu-id="849e3-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="849e3-125">Настройка возможности обнаружения новых закрытых команд</span><span class="sxs-lookup"><span data-stu-id="849e3-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="849e3-126">Когда владелец группы создает закрытую команду, она может сделать ее обнаруживаемой, настроив параметр обнаружения группы.</span><span class="sxs-lookup"><span data-stu-id="849e3-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="849e3-127">По умолчанию новые закрытые команды доступны для поиска и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="849e3-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="849e3-128">Если владелец команды не хочет, чтобы частная группа отображалась в результатах поиска и предложениях, владелец может отключить этот параметр, выбрав команду **изменить параметры** рядом с **этой командой**.</span><span class="sxs-lookup"><span data-stu-id="849e3-128">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Снимок экрана с параметрами обнаружения для новых закрытых команд](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="849e3-130">Настройка возможности обнаружения существующих закрытых команд</span><span class="sxs-lookup"><span data-stu-id="849e3-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="849e3-131">Владельцы групп могут настроить параметр обнаружения для существующей закрытой команды прямо в разделе Параметры группы, а администраторы могут сделать это с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="849e3-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="849e3-132">В параметрах группы</span><span class="sxs-lookup"><span data-stu-id="849e3-132">In team settings</span></span>

<span data-ttu-id="849e3-133">В Teams перейдите в раздел закрытая группа и выберите пункт **Дополнительные параметры** > **управления командой**.</span><span class="sxs-lookup"><span data-stu-id="849e3-133">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="849e3-134">На вкладке **Параметры** разверните узел **обнаружение групп**, а затем снимите или установите флажок **включить обнаружение** .</span><span class="sxs-lookup"><span data-stu-id="849e3-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Снимок экрана с параметрами обнаружения для существующих закрытых команд](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="849e3-136">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="849e3-136">Using PowerShell</span></span>

<span data-ttu-id="849e3-137">С помощью командлета **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** вы можете отключить или включить параметр обнаружения для существующей закрытой команды.</span><span class="sxs-lookup"><span data-stu-id="849e3-137">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="849e3-138">Вот пример того, как сделать команду обнаруживаемой.</span><span class="sxs-lookup"><span data-stu-id="849e3-138">Here's an example of how to make a team discoverable:</span></span>
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="849e3-139">Вы можете использовать этот командлет в сценарии, чтобы настроить параметр обнаружения для существующих закрытых групп в массовом режиме.</span><span class="sxs-lookup"><span data-stu-id="849e3-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="849e3-140">Определение того, могут ли пользователи определять закрытые группы</span><span class="sxs-lookup"><span data-stu-id="849e3-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="849e3-141">Администратор также может управлять тем, какие пользователи в вашей организации смогут находить закрытые команды в результатах поиска и предложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="849e3-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="849e3-142">Создайте политику с помощью командлета **[New-кстеамсчаннелсполици](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** , а затем назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="849e3-142">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="849e3-143">Установите для параметра **алловприватетеамдисковери** значение **true** , чтобы пользователи, которым назначена политика, могли видеть обнаруженные частные команды в результатах поиска и предложения.</span><span class="sxs-lookup"><span data-stu-id="849e3-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="849e3-144">При задании значения **false** для параметра **алловприватетеамдисковери** удаляются все обнаруживаемые закрытые группы из результатов поиска и предложения для пользователей, которым назначена политика.</span><span class="sxs-lookup"><span data-stu-id="849e3-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="849e3-145">По умолчанию для **алловприватетеамдисковери** установлено **значение true** для всех пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="849e3-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="849e3-146">В этом примере мы создаем политику с именем Вендорполици, которая не позволяет пользователям обнаруживать закрытые команды, которые были доступны для обнаружения, а затем назначает политику пользователю с именем vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="849e3-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="849e3-147">Закрытые команды, которые не могут быть обнаружены, никогда не отображаются в результатах поиска и предложениях, независимо от параметра политики.</span><span class="sxs-lookup"><span data-stu-id="849e3-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="849e3-148">Например, если отключить параметр обнаружения для закрытой команды, пользователи не смогут найти команду, даже если параметр **алловприватетеамдисковери** имеет значение **true** в параметре политики для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="849e3-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="849e3-149">См. также</span><span class="sxs-lookup"><span data-stu-id="849e3-149">Related topics</span></span>
- [<span data-ttu-id="849e3-150">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="849e3-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
