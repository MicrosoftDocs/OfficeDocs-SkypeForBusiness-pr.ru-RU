---
title: Улучшите существующие группы Office 365 с группами Майкрософт
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Сведения об улучшении групп Office 365 с помощью Microsoft Teams за счет приглашения в команду с помощью списка рассылки, добавления групп безопасности с поддержкой почты и т. п.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13b34da03c35706fafb02a4e9e02eab629a4a399
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568418"
---
<a name="enhance-existing-office-365-groups-with-microsoft-teams"></a><span data-ttu-id="05dfa-103">Улучшите существующие группы Office 365 с группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="05dfa-103">Enhance existing Office 365 groups with Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="05dfa-104">Пользователи Microsoft Teams могут улучшить имеющуюся группу Office 365 с помощью функций Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="05dfa-104">Microsoft Teams users can enhance an existing Office 365 Group with Microsoft Teams functionality.</span></span> <span data-ttu-id="05dfa-105">Общедоступную группу Office 365 можно улучшить, если число ее участников не превышает 2500.</span><span class="sxs-lookup"><span data-stu-id="05dfa-105">When looking at enhancing a public Office 365 Group, users can do that if the number of members is equal to or less than 2500.</span></span>

<span data-ttu-id="05dfa-106">Для этого пользователям следует выполнить процедуру создания команды из клиента Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="05dfa-106">To do this, users should go through the flow of creating a new team from the Microsoft Teams client.</span></span> <span data-ttu-id="05dfa-107">Выберите команду **Создать группу из существующей группы Office 365** в нижней части экрана, а затем выберите существующую группу, который необходимо расширить с группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05dfa-107">Select **Create a team from an existing Office 365 group** at the bottom of the screen and then choose the existing group that you want to enhance with Microsoft Teams.</span></span> <span data-ttu-id="05dfa-108">Участники этой группы автоматически добавляются в команду.</span><span class="sxs-lookup"><span data-stu-id="05dfa-108">Existing group members will be added as members to the team automatically.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05dfa-109">Только владелец группы Office 365 иметь разрешение для улучшения существующей группы с группами Майкрософт и этой группы должны содержать меньше, чем 2500 пользователей.</span><span class="sxs-lookup"><span data-stu-id="05dfa-109">Only Office 365 Group owners have permission to enhance an existing group  with Microsoft Teams, and that group must contain less than 2500 users.</span></span> <span data-ttu-id="05dfa-110">Команды, которые уже были улучшены не будет отображаться в списке.</span><span class="sxs-lookup"><span data-stu-id="05dfa-110">Teams that have already been enhanced will not show up in the list.</span></span>
>
><span data-ttu-id="05dfa-111">Параметр **создать группы из существующей группы Office 365** не будет доступен, пока не выполнены следующие условия.</span><span class="sxs-lookup"><span data-stu-id="05dfa-111">The **Create a team from an existing Office 365 group** option will not be available unless these conditions have been met.</span></span>

<span data-ttu-id="05dfa-112">Пользователи также могут приглашать участников в команду с помощью списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="05dfa-112">Users can also invite a distribution list to a team, and the members of that distribution list will be added to the team.</span></span> <span data-ttu-id="05dfa-113">Это осуществляется с помощью однократной синхронизации, а репликация последующих изменений членства в группе, вносимых в этот список рассылки, в Teams не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="05dfa-113">This is a one-time sync, and later changes in group membership in the distribution list will not be replicated to Teams.</span></span> 

![Последовательность снимков экрана, показывающая приглашение списка рассылки и его участников в команду.](media/Enhance_Existing_Office_365_groups_with_Microsoft_Teams_image2.png)

<span data-ttu-id="05dfa-115">Вы также можете добавлять группы безопасности с поддержкой почты в качестве участников команды.</span><span class="sxs-lookup"><span data-stu-id="05dfa-115">You can also add mail-enabled security groups as members of a team.</span></span> <span data-ttu-id="05dfa-116">Однако если позднее вы добавите в эту группу безопасности других участников, они не будут добавлены в команду автоматически.</span><span class="sxs-lookup"><span data-stu-id="05dfa-116">But, if you later add more members to the security group, those members are not automatically added to the team.</span></span> <span data-ttu-id="05dfa-117">Нужно отдельно добавить новых участников либо повторно добавить в команду соответствующую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="05dfa-117">You must add the new members separately or re-add the security group to the team.</span></span> <span data-ttu-id="05dfa-118">(Во втором случае благодаря дедупликации участники будут представлены в единственном экземпляре.)</span><span class="sxs-lookup"><span data-stu-id="05dfa-118">(If you re-add the security group, deduplication makes sure members are added only once.)</span></span>

<span data-ttu-id="05dfa-119">Для групп Office 365 имеется два вида параметров конфиденциальности — **общедоступные и частные**.</span><span class="sxs-lookup"><span data-stu-id="05dfa-119">There are two types of privacy settings with Office 365 groups, **public and private**.</span></span> <span data-ttu-id="05dfa-120">Хотя для Microsoft Teams можно включить оба типа групп, между ними есть небольшие различия с точки зрения самообслуживания.</span><span class="sxs-lookup"><span data-stu-id="05dfa-120">Whereas both group types can be enabled for Microsoft Teams, there is a slight difference when it comes to self-service.</span></span>

-   <span data-ttu-id="05dfa-121">Пользователи могут искать общедоступные группы и самостоятельно присоединяться к ним без утверждения владельца команды.</span><span class="sxs-lookup"><span data-stu-id="05dfa-121">Users can search for public groups and can join by themselves without a need for team owner’s approval.</span></span>

-   <span data-ttu-id="05dfa-122">Закрытые группы недоступны для поиска, и пользователи не могут присоединиться к ним, пока владелец команды не добавит их в качестве участника.</span><span class="sxs-lookup"><span data-stu-id="05dfa-122">Private groups are not searchable, and users cannot join unless a team owner add them as a member.</span></span>

<span data-ttu-id="05dfa-123">Владелец существующей закрытой группы Office 365 может использовать членство в ней для создания команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="05dfa-123">When creating a new team in Microsoft Teams, an owner of an existing private Office 365 group has an option to use the membership in the Office 365 group to create the team.</span></span> <span data-ttu-id="05dfa-124">Пользователи могут добавить имеющиеся файлы SharePoint и OneNote, добавив вкладку для SharePoint и объединив файлы OneNote.</span><span class="sxs-lookup"><span data-stu-id="05dfa-124">Users can add their existing SharePoint and OneNote files by adding a tab for SharePoint and merging OneNote files.</span></span>
