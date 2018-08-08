---
title: Улучшение имеющихся групп Office 365 с помощью Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Сведения об улучшении групп Office 365 с помощью Microsoft Teams за счет приглашения в команду с помощью списка рассылки, добавления групп безопасности с поддержкой почты и т. п.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec96b186a37df59fd09f0083d0dd1d174819ba59
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "18999129"
---
<a name="enhance-existing-office-365-groups-with-microsoft-teams"></a><span data-ttu-id="17948-103">Улучшение имеющихся групп Office 365 с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17948-103">Enhance Existing Office 365 groups with Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="17948-104">Пользователи Microsoft Teams могут улучшить имеющуюся группу Office 365 с помощью функций Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17948-104">Microsoft Teams users can enhance an existing Office 365 Group with Microsoft Teams functionality.</span></span> <span data-ttu-id="17948-105">Общедоступную группу Office 365 можно улучшить, если число ее участников не превышает 2500.</span><span class="sxs-lookup"><span data-stu-id="17948-105">When looking at enhancing a public Office 365 Group, users can do that if the number of members is equal to or less than 2500.</span></span>

<span data-ttu-id="17948-106">Для этого пользователям следует выполнить процедуру создания команды из клиента Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17948-106">To do this, users should go through the flow of creating a new team from the Microsoft Teams client.</span></span> <span data-ttu-id="17948-107">Выберите параметр **"Да, добавить возможности Microsoft Teams"** в нижней части экрана и затем существующую группу, которую хотите улучшить с помощью Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17948-107">Select **“Yes, add Microsoft Teams functionality”** at the bottom of the screen and then choose the existing group that they want to enhance with Microsoft Teams.</span></span> <span data-ttu-id="17948-108">Участники этой группы автоматически добавляются в команду.</span><span class="sxs-lookup"><span data-stu-id="17948-108">Existing group members will be added as members to the team automatically.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="17948-109">Правом добавлять в существующую группу возможности Microsoft Teams обладают только владельцы группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="17948-109">Only Office 365 Group owners have permission to enhance an existing group with Microsoft Teams.</span></span> 

<span data-ttu-id="17948-110">Пользователи также могут приглашать участников в команду с помощью списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="17948-110">Users can also invite a distribution list to a team, and the members of that distribution list will be added to the team.</span></span> <span data-ttu-id="17948-111">Это осуществляется с помощью однократной синхронизации, а репликация последующих изменений членства в группе, вносимых в этот список рассылки, в Teams не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="17948-111">This is a one-time sync, and later changes in group membership in the distribution list will not be replicated to Teams.</span></span> 

![Последовательность снимков экрана, показывающая приглашение списка рассылки и его участников в команду.](media/Enhance_Existing_Office_365_groups_with_Microsoft_Teams_image2.png)

<span data-ttu-id="17948-113">Вы также можете добавлять группы безопасности с поддержкой почты в качестве участников команды.</span><span class="sxs-lookup"><span data-stu-id="17948-113">You can also add mail-enabled security groups as members of a team.</span></span> <span data-ttu-id="17948-114">Однако если позднее вы добавите в эту группу безопасности других участников, они не будут добавлены в команду автоматически.</span><span class="sxs-lookup"><span data-stu-id="17948-114">But, if you later add more members to the security group, those members are not automatically added to the team.</span></span> <span data-ttu-id="17948-115">Нужно отдельно добавить новых участников либо повторно добавить в команду соответствующую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="17948-115">You must add the new members separately or re-add the security group to the team.</span></span> <span data-ttu-id="17948-116">(Во втором случае благодаря дедупликации участники будут представлены в единственном экземпляре.)</span><span class="sxs-lookup"><span data-stu-id="17948-116">(If you re-add the security group, deduplication makes sure members are added only once.)</span></span>

<span data-ttu-id="17948-117">Для групп Office 365 имеется два вида параметров конфиденциальности — **общедоступные и частные**.</span><span class="sxs-lookup"><span data-stu-id="17948-117">There are two types of privacy settings with Office 365 groups, **public and private**.</span></span> <span data-ttu-id="17948-118">Хотя для Microsoft Teams можно включить оба типа групп, между ними есть небольшие различия с точки зрения самообслуживания.</span><span class="sxs-lookup"><span data-stu-id="17948-118">Whereas both group types can be enabled for Microsoft Teams, there is a slight difference when it comes to self-service.</span></span>

-   <span data-ttu-id="17948-119">Пользователи могут искать общедоступные группы и самостоятельно присоединяться к ним без утверждения владельца команды.</span><span class="sxs-lookup"><span data-stu-id="17948-119">Users can search for public groups and can join by themselves without a need for team owner’s approval.</span></span>

-   <span data-ttu-id="17948-120">Закрытые группы недоступны для поиска, и пользователи не могут присоединиться к ним, пока владелец команды не добавит их в качестве участника.</span><span class="sxs-lookup"><span data-stu-id="17948-120">Private groups are not searchable, and users cannot join unless a team owner add them as a member.</span></span>

<span data-ttu-id="17948-121">Владелец существующей закрытой группы Office 365 может использовать членство в ней для создания команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17948-121">When creating a new team in Microsoft Teams, an owner of an existing private Office 365 group has an option to use the membership in the Office 365 group to create the team.</span></span> <span data-ttu-id="17948-122">Пользователи могут добавить имеющиеся файлы SharePoint и OneNote, добавив вкладку для SharePoint и объединив файлы OneNote.</span><span class="sxs-lookup"><span data-stu-id="17948-122">Users can add their existing SharePoint and OneNote files by adding a tab for SharePoint and merging OneNote files.</span></span>
