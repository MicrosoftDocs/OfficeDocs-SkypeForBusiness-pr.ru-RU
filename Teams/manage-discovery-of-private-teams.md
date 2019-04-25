---
title: Управление обнаружения закрытый группами в группах Майкрософт
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как управлять ли пользователями группами Майкрософт с помощью предложения в результатах команды коллекции и поиска для обнаружения частных групп.
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262768"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="1f36c-103">Управление обнаружения закрытый группами в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1f36c-103">Manage discovery of private teams in Microsoft Teams</span></span>

<span data-ttu-id="1f36c-104">Рабочая группа администраторов и владельцев можно управлять ли закрытый группами для обнаружения с группами Майкрософт пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1f36c-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="1f36c-105">При обнаруживаемые частной группы отображается в результатах поиска и включается в предложений в коллекции группы наряду с общей группы в группах.</span><span class="sxs-lookup"><span data-stu-id="1f36c-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="1f36c-106">Это упрощает для пользователей поиск и найдите закрытый групп, которые они хотят присоединиться к.</span><span class="sxs-lookup"><span data-stu-id="1f36c-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="1f36c-107">Пользователи могут запрашивать для присоединения к частной группы которого владелец группы могут утвердить либо запретить.</span><span class="sxs-lookup"><span data-stu-id="1f36c-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="1f36c-108">Обзор общих групп, закрытый групп и обнаружения в группах</span><span class="sxs-lookup"><span data-stu-id="1f36c-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="1f36c-109">Большинство организаций имеют следующие типы групп - общедоступных групп, поддерживающего обнаружение закрытый групп и невидимый закрытый группами.</span><span class="sxs-lookup"><span data-stu-id="1f36c-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Коллекция групп](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="1f36c-111">Общедоступные группы</span><span class="sxs-lookup"><span data-stu-id="1f36c-111">Public teams</span></span>

<span data-ttu-id="1f36c-112">Общедоступные команды доступны для всех пользователей в вашей организации для присоединения к.</span><span class="sxs-lookup"><span data-stu-id="1f36c-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="1f36c-113">Общедоступных групп отображаются всем пользователям в коллекции группы и пользователи могут присоединиться к общедоступной группы без необходимости получение утверждения от владельца группы.</span><span class="sxs-lookup"><span data-stu-id="1f36c-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="1f36c-114">Примеры команд общедоступных включают группы для обсуждения новостей в технологии, рабочая группа, чтобы получить себя свои отзывы и предложения для продуктов и группы для пассажирами людей для работы.</span><span class="sxs-lookup"><span data-stu-id="1f36c-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="1f36c-115">Обнаруживаемые закрытый групп</span><span class="sxs-lookup"><span data-stu-id="1f36c-115">Discoverable private teams</span></span>

<span data-ttu-id="1f36c-116">Обнаруживаемые закрытый групп можно присоединиться только в том случае, когда владелец группы добавляет пользователей к ним.</span><span class="sxs-lookup"><span data-stu-id="1f36c-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="1f36c-117">При внесении частной группы обнаруживаемые, группа включен в список предложенного групп и результатов поиска в коллекцию групп.</span><span class="sxs-lookup"><span data-stu-id="1f36c-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="1f36c-118">Используйте обнаруживаемые закрытый групп для проектов и групп в организации, всем пользователям принять во внимание и где доступ к бесед и файлы рабочих групп нужно управлять.</span><span class="sxs-lookup"><span data-stu-id="1f36c-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="1f36c-119">Примерами являются группы для вашего отдела Кадров, группы для всех диспетчеров в вашей организации и группы для руководителя и прямые отчеты.</span><span class="sxs-lookup"><span data-stu-id="1f36c-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="1f36c-120">Обнаруживаемые не являющиеся закрытый групп</span><span class="sxs-lookup"><span data-stu-id="1f36c-120">Non-discoverable private teams</span></span>

<span data-ttu-id="1f36c-121">Обнаруживаемые не являющиеся закрытый групп можно присоединиться только в том случае, если владелец группы Добавление пользователей к ним.</span><span class="sxs-lookup"><span data-stu-id="1f36c-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="1f36c-122">При внесении частной группы не поддерживающего обнаружение, скрытым в списке предложенного групп и удалены из результатов поиска в коллекцию групп.</span><span class="sxs-lookup"><span data-stu-id="1f36c-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="1f36c-123">Используйте невидимый групп для совместной работы над разделы конфиденциальных и конфиденциальными.</span><span class="sxs-lookup"><span data-stu-id="1f36c-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="1f36c-124">Примеры включают группы для обсуждения предстоящие приобретения и группы для обсуждения изменений в вашей организации стратегического направлении.</span><span class="sxs-lookup"><span data-stu-id="1f36c-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="1f36c-125">Установка новых частных рабочих групп, поддерживающего обнаружение ли</span><span class="sxs-lookup"><span data-stu-id="1f36c-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="1f36c-126">При создании владельцем группы частной группы, можно сделать видимым, настроив проектной обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1f36c-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="1f36c-127">По умолчанию новых частных рабочих групп, для поиска и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1f36c-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="1f36c-128">Если владелец группы не хотите, чтобы закрытый групп, отображаемых в результатах поиска и предложений, их можно отключить параметр, выбрав **изменить параметр** рядом с элементом **данной группы для поиска и обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="1f36c-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![параметр обнаружения для новых частных рабочих групп](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="1f36c-130">Задать существующий закрытый групп, поддерживающего обнаружение ли</span><span class="sxs-lookup"><span data-stu-id="1f36c-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="1f36c-131">Владельцев группы можно задать параметр обнаружения для существующего частной группы непосредственно в диалоговом окне настройки групп и "Администраторы" можно сделать с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f36c-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="1f36c-132">В параметрах группы</span><span class="sxs-lookup"><span data-stu-id="1f36c-132">In team settings</span></span>

<span data-ttu-id="1f36c-133">В группах, перейдите к частной группы, нажмите кнопку **Дополнительные параметры ˙˙˙** > **Управление группы**.</span><span class="sxs-lookup"><span data-stu-id="1f36c-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="1f36c-134">На вкладке « **Параметры** » разверните узел **группы обнаружения**и снимите или установите флажок **включения обнаружения** .</span><span class="sxs-lookup"><span data-stu-id="1f36c-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![параметр обнаружения для существующий закрытый групп](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="1f36c-136">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f36c-136">Using PowerShell</span></span>

<span data-ttu-id="1f36c-137">Командлет **Set-подключения группой разработки** для отключить или включить параметр обнаружения для существующей закрытый рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="1f36c-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="1f36c-138">Ниже приведен пример того, как сделать видимым команды:</span><span class="sxs-lookup"><span data-stu-id="1f36c-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="1f36c-139">Этот командлет можно использовать в сценарии для задайте для параметра обнаружения существующий закрытый команд в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="1f36c-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="1f36c-140">Указать, следует ли пользователи могут обнаруживать закрытый групп</span><span class="sxs-lookup"><span data-stu-id="1f36c-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="1f36c-141">Как администратора можно управлять пользователей в вашей организации, которые разрешены для обнаружения частных групп в результатах поиска и предложений в группах.</span><span class="sxs-lookup"><span data-stu-id="1f36c-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="1f36c-142">Создание политики с помощью командлета **New-CsTeamsChannelsPolicy** и назначьте политику для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f36c-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="1f36c-143">Установите для параметра **AllowPrivateTeamDiscovery** значение **true,** чтобы пользователи, которым назначена политика, чтобы увидеть обнаруживаемые закрытый группами в результатах поиска и предложений.</span><span class="sxs-lookup"><span data-stu-id="1f36c-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="1f36c-144">Для параметра **AllowPrivateTeamDiscovery** **значение false** удаляет все обнаруживаемые частной группы из результатов поиска и предложений для пользователей, которым назначена политика.</span><span class="sxs-lookup"><span data-stu-id="1f36c-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="1f36c-145">По умолчанию **AllowPrivateTeamDiscovery** имеет значение **true** для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="1f36c-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="1f36c-146">В этом примере мы создать политику с именем VendorPolicy, который запрещает пользователям обнаружение каким-либо закрытый группам, которые внесены обнаруживаемые, и затем мы назначьте политику для пользователя с именем vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="1f36c-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="1f36c-147">Закрытый групп, которые не являются обнаруживаемые никогда не показаны в результатах поиска и предложений, независимо от того, параметр политики.</span><span class="sxs-lookup"><span data-stu-id="1f36c-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="1f36c-148">Например при выключении параметра обнаружения для закрытого группы Пользователи не могут обнаруживать группы, несмотря на то, что параметр **AllowPrivateTeamDiscovery** имеет значение **true** в параметр политики для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f36c-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1f36c-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1f36c-149">Related topics</span></span>
- [<span data-ttu-id="1f36c-150">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="1f36c-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)