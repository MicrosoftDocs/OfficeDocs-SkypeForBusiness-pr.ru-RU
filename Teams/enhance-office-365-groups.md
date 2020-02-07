---
title: Расширение существующих групп Office 365 с помощью Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
description: Сведения об улучшении групп Office 365 с помощью Microsoft Teams за счет приглашения в команду с помощью списка рассылки, добавления групп безопасности с поддержкой почты и т. п.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99afab167cdc865214f621d9994c3b5d124e98ed
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832919"
---
<a name="enhance-existing-office-365-groups-with-microsoft-teams"></a><span data-ttu-id="dd9e5-103">Расширение существующих групп Office 365 с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd9e5-103">Enhance existing Office 365 groups with Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="dd9e5-104">Пользователи Microsoft Teams могут расширить существующую группу Office 365 с помощью функций Teams.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-104">Microsoft Teams users can enhance an existing Office 365 Group with Teams functionality.</span></span> <span data-ttu-id="dd9e5-105">Когда вы просматриваете улучшенную группу Office 365, пользователи могут сделать это, если количество пользователей равно или меньше 5 000.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-105">When looking at enhancing a public Office 365 Group, users can do that if the number of members is equal to or less than 5,000.</span></span>

<span data-ttu-id="dd9e5-106">Для этого пользователям следует выполнить процедуру создания команды из клиента Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-106">To do this, users should go through the flow of creating a new team from the Microsoft Teams client.</span></span> <span data-ttu-id="dd9e5-107">Выберите команду **создать из** > **группы Office 365**, а затем выберите существующую группу, которую вы хотите усовершенствовать с помощью Teams.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-107">Select **Create from** > **Office 365 group**, and then choose the existing group that you want to enhance with Teams.</span></span> <span data-ttu-id="dd9e5-108">Участники этой группы автоматически добавляются в команду.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-108">Existing group members will be added as members to the team automatically.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd9e5-109">Только владельцы групп Office 365 имеют разрешение на расширение существующей группы с помощью Teams, и эта группа должна содержать менее 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-109">Only Office 365 Group owners have permission to enhance an existing group  with Teams, and that group must contain less than 5,000 users.</span></span> <span data-ttu-id="dd9e5-110">Команды, которые уже были улучшены, не отображаются в списке.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-110">Teams that have already been enhanced will not show up in the list.</span></span>
>
><span data-ttu-id="dd9e5-111">Параметр для создания команды из группы Office 365 будет недоступен, пока не будут выполнены эти условия.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-111">The option to create a team from an Office 365 Group will not be available unless these conditions have been met.</span></span>

<span data-ttu-id="dd9e5-112">Пользователи также могут приглашать участников в команду с помощью списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-112">Users can also invite a distribution list to a team, and the members of that distribution list will be added to the team.</span></span> <span data-ttu-id="dd9e5-113">Это единовременно добавленные и более поздние изменения членства в группах в списке рассылки не реплицируются и не синхронизируются в Teams.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-113">This is a one-time add, and later changes in group membership in the distribution list will not be replicated or synced to Teams.</span></span>

![Снимок экрана: команда для создания группы из группы Office 365.](media/Enhance_Existing_Office_365_groups_with_Microsoft_Teams_image2.png)

<span data-ttu-id="dd9e5-115">Вы также можете добавлять группы безопасности с поддержкой почты в качестве участников команды.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-115">You can also add mail-enabled security groups as members of a team.</span></span> <span data-ttu-id="dd9e5-116">Однако если позднее вы добавите в эту группу безопасности других участников, они не будут добавлены в команду автоматически.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-116">But, if you later add more members to the security group, those members are not automatically added to the team.</span></span> <span data-ttu-id="dd9e5-117">Нужно отдельно добавить новых участников либо повторно добавить в команду соответствующую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-117">You must add the new members separately or re-add the security group to the team.</span></span> <span data-ttu-id="dd9e5-118">(Во втором случае благодаря дедупликации участники будут представлены в единственном экземпляре.)</span><span class="sxs-lookup"><span data-stu-id="dd9e5-118">(If you re-add the security group, deduplication makes sure members are added only once.)</span></span>

<span data-ttu-id="dd9e5-119">Для групп Office 365 имеется два вида параметров конфиденциальности — **общедоступные и частные**.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-119">There are two types of privacy settings with Office 365 groups, **public and private**.</span></span> <span data-ttu-id="dd9e5-120">В то время как оба типа групп могут быть включены для Teams, существует небольшая разница в том, что они поступают на самообслуживание.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-120">Whereas both group types can be enabled for Teams, there is a slight difference when it comes to self-service.</span></span>

-   <span data-ttu-id="dd9e5-121">Пользователи могут искать общедоступные группы и самостоятельно присоединяться к ним без утверждения владельца команды.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-121">Users can search for public groups and can join by themselves without a need for team owner’s approval.</span></span>

-   <span data-ttu-id="dd9e5-122">Закрытые группы недоступны для поиска, и пользователи не могут присоединиться к ним, пока владелец команды не добавит их в качестве участника.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-122">Private groups are not searchable, and users cannot join unless a team owner add them as a member.</span></span>

<span data-ttu-id="dd9e5-123">Когда вы создаете новую группу в Teams, владелец существующей группы Office 365 имеет возможность использовать членство в группе Office 365 для создания команды.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-123">When creating a new team in Teams, an owner of an existing private Office 365 group has an option to use the membership in the Office 365 group to create the team.</span></span> <span data-ttu-id="dd9e5-124">Пользователи могут добавить имеющиеся файлы SharePoint и OneNote, добавив вкладку для SharePoint и объединив файлы OneNote.</span><span class="sxs-lookup"><span data-stu-id="dd9e5-124">Users can add their existing SharePoint and OneNote files by adding a tab for SharePoint and merging OneNote files.</span></span>
