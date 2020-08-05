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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как управлять возможностью обнаружения конфиденциальных команд пользователями Microsoft Teams с помощью предложений в галерее группы и в результатах поиска.
ms.openlocfilehash: e06a9511d8198a069c3dccfdbbbacf3d3f1b2c42
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46554699"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="ac5fe-103">Управление обнаружением закрытых команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac5fe-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac5fe-104">На основе отзывов пользователей мы отключаем эту функцию, вступают в силу до 31 августа 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-104">Based on customer feedback, we're disabling this feature, effective August 31, 2020.</span></span> <span data-ttu-id="ac5fe-105">Это означает, что после 31 августа 2020 вы больше не сможете сделать закрытыми команды обнаруживаемыми, и все существующие и новые закрытые команды больше не будут доступны для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-105">This means that after August 31, 2020, you will no longer be able to set private teams to be discoverable and all existing and new private teams will no longer be discoverable.</span></span> <span data-ttu-id="ac5fe-106">Дополнительные сведения можно найти в [статье план Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span><span class="sxs-lookup"><span data-stu-id="ac5fe-106">To learn more, see the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="ac5fe-107">Администраторы и владельцы групп могут определять, могут ли быть обнаружены частные команды для пользователей Microsoft Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-107">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="ac5fe-108">Если частная группа является обнаруживаемой, она отображается в результатах поиска и включается в предложения коллекции групп наряду с общедоступными группами в Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-108">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="ac5fe-109">Благодаря этому пользователи смогут легко находить и находить закрытые группы, к которым они хотят присоединиться.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-109">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="ac5fe-110">Пользователи могут попросить присоединиться к закрытой команде, а владелец команды может утвердить или отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-110">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="ac5fe-111">Общие сведения об общедоступных группах, частных командах и обнаружении в Teams</span><span class="sxs-lookup"><span data-stu-id="ac5fe-111">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="ac5fe-112">Большинство организаций обладают следующими видами команд: общедоступные группы, обнаруживаемые закрытые команды и закрытые группы, не обнаруживаемые.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-112">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Снимок экрана с коллекцией групп](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="ac5fe-114">Общедоступные группы</span><span class="sxs-lookup"><span data-stu-id="ac5fe-114">Public teams</span></span>

<span data-ttu-id="ac5fe-115">Общедоступные команды доступны для всех пользователей в вашей организации, чтобы присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-115">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="ac5fe-116">Общедоступные команды видны всем пользователям в коллекции Teams, и пользователи могут присоединиться к общедоступной команде, не требуя утверждения от владельца группы.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-116">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="ac5fe-117">Примеры общедоступных команд включают в себя группу, в которой рассказывается о технологиях, группе для получения отзывов о ваших продуктах и команде для людей, carpooling работать.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-117">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="ac5fe-118">Обнаруживаемые закрытые группы</span><span class="sxs-lookup"><span data-stu-id="ac5fe-118">Discoverable private teams</span></span>

<span data-ttu-id="ac5fe-119">Обнаруживаемые закрытые команды могут быть присоединены, только когда владелец группы добавляет в них пользователей.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-119">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="ac5fe-120">Если вы сделаете личную команду обнаруживаемой, она будет включена в список предложенных команд и результатов поиска в коллекции Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-120">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="ac5fe-121">Используйте обнаруживаемые закрытые команды для проектов и групп в Организации, где все знают, и где доступ к беседам и файлам в команде нужно контролировать.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-121">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="ac5fe-122">Примеры: группа для отдела кадров, группа для всех руководителей в Организации и группа для руководителя и их непосредственных отчетов.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-122">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="ac5fe-123">Не обнаруживаемые закрытые группы</span><span class="sxs-lookup"><span data-stu-id="ac5fe-123">Non-discoverable private teams</span></span>

<span data-ttu-id="ac5fe-124">Необнаруживаемые закрытые команды могут быть присоединены, только когда владелец группы добавляет в них пользователей.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-124">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="ac5fe-125">Если вы сделаете закрытую команду необнаруживаемой, она будет скрыта от списка предлагаемых групп и удалена из результатов поиска в коллекции Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-125">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="ac5fe-126">Использование необнаруживаемых команд для совместной работы с конфиденциальными и весьма конфиденциальными разделами.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-126">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="ac5fe-127">Примеры включают в себя команду для обсуждения предстоящего приобретения и команды обсудить изменения в стратегическом направлении Организации.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-127">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="ac5fe-128">Настройка возможности обнаружения новых закрытых команд</span><span class="sxs-lookup"><span data-stu-id="ac5fe-128">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="ac5fe-129">Когда владелец группы создает закрытую команду, она может сделать ее обнаруживаемой, настроив параметр обнаружения группы.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-129">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="ac5fe-130">По умолчанию новые закрытые команды доступны для поиска и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-130">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="ac5fe-131">Если владелец команды не хочет, чтобы частная группа отображалась в результатах поиска и предложениях, владелец может отключить этот параметр, выбрав команду **изменить параметры** рядом с **этой командой**.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-131">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Снимок экрана с параметрами обнаружения для новых закрытых команд](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="ac5fe-133">Настройка возможности обнаружения существующих закрытых команд</span><span class="sxs-lookup"><span data-stu-id="ac5fe-133">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="ac5fe-134">Владельцы групп могут настроить параметр обнаружения для существующей закрытой команды прямо в разделе Параметры группы, а администраторы могут сделать это с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-134">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="ac5fe-135">В параметрах группы</span><span class="sxs-lookup"><span data-stu-id="ac5fe-135">In team settings</span></span>

<span data-ttu-id="ac5fe-136">В Teams перейдите в раздел закрытая группа и выберите пункт **Дополнительные параметры**  >  **управления командой**.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-136">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="ac5fe-137">На вкладке **Параметры** разверните узел **обнаружение групп**, а затем снимите или установите флажок **включить обнаружение** .</span><span class="sxs-lookup"><span data-stu-id="ac5fe-137">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Снимок экрана с параметрами обнаружения для существующих закрытых команд](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="ac5fe-139">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac5fe-139">Using PowerShell</span></span>

<span data-ttu-id="ac5fe-140">С помощью командлета **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** вы можете отключить или включить параметр обнаружения для существующей закрытой команды.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-140">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="ac5fe-141">Вот пример того, как сделать команду обнаруживаемой.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-141">Here's an example of how to make a team discoverable:</span></span>
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="ac5fe-142">Вы можете использовать этот командлет в сценарии, чтобы настроить параметр обнаружения для существующих закрытых групп в массовом режиме.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-142">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="ac5fe-143">Определение того, могут ли пользователи определять закрытые группы</span><span class="sxs-lookup"><span data-stu-id="ac5fe-143">Set whether users can discover private teams</span></span>

<span data-ttu-id="ac5fe-144">Администратор также может управлять тем, какие пользователи в вашей организации смогут находить закрытые команды в результатах поиска и предложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-144">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="ac5fe-145">Создайте политику с помощью командлета **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** , а затем назначьте политику пользователям.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-145">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="ac5fe-146">Установите для параметра **AllowPrivateTeamDiscovery** значение **true** , чтобы пользователи, которым назначена политика, могли видеть обнаруженные частные команды в результатах поиска и предложения.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-146">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="ac5fe-147">При задании значения **false** для параметра **AllowPrivateTeamDiscovery** удаляются все обнаруживаемые закрытые группы из результатов поиска и предложения для пользователей, которым назначена политика.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-147">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="ac5fe-148">По умолчанию для **AllowPrivateTeamDiscovery** установлено **значение true** для всех пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-148">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="ac5fe-149">В этом примере мы создаем политику с именем VendorPolicy, которая не позволяет пользователям обнаруживать закрытые команды, которые были доступны для обнаружения, а затем назначает политику пользователю с именем vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-149">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="ac5fe-150">Закрытые команды, которые не могут быть обнаружены, никогда не отображаются в результатах поиска и предложениях, независимо от параметра политики.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-150">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="ac5fe-151">Например, если отключить параметр обнаружения для закрытой команды, пользователи не смогут найти команду, даже если параметр **AllowPrivateTeamDiscovery** имеет значение **true** в параметре политики для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-151">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac5fe-152">См. также</span><span class="sxs-lookup"><span data-stu-id="ac5fe-152">Related topics</span></span>
- [<span data-ttu-id="ac5fe-153">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="ac5fe-153">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
