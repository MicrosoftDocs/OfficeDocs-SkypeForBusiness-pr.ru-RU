---
title: Высокая доступность (средство планирования)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Основная схема высокой доступности большинства ролей сервера в Skype для бизнеса Server основана на избыточности сервера с помощью пулинга. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093317"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="160ad-104">Высокая доступность (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="160ad-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="160ad-105">Основная схема высокой доступности большинства ролей сервера в Skype для бизнеса Server основана на избыточности сервера с помощью пулинга.</span><span class="sxs-lookup"><span data-stu-id="160ad-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="160ad-106">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="160ad-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="160ad-107">Для обеспечения высокой доступности Skype для бизнес-сервера требуется по крайней мере два передних конечных сервера.</span><span class="sxs-lookup"><span data-stu-id="160ad-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="160ad-108">Средство планирования использует следующие критерии, чтобы определить, будут ли добавлены дополнительные серверы для обеспечения высокой доступности:</span><span class="sxs-lookup"><span data-stu-id="160ad-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="160ad-109">Если развертывание содержит два или более серверов переднего плана, средство планирования не добавляет дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="160ad-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="160ad-110">Если развертывание содержит Edge Server, добавляется дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="160ad-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="160ad-111">Если развертывание содержит постоянный чат, средство планирования добавит дополнительный сервер, но не увеличит номер пула.</span><span class="sxs-lookup"><span data-stu-id="160ad-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="160ad-112">Например, если развертывание уже содержит четыре сервера, средство планирования предложит добавить дополнительный сервер (в общей сложности пять серверов), но будет поддерживать один пул.</span><span class="sxs-lookup"><span data-stu-id="160ad-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="160ad-113">Постоянный чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="160ad-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="160ad-114">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="160ad-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="160ad-115">Дополнительные сведения см. в [обновлениях Skype для бизнеса до Microsoft Teams.](/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="160ad-115">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="160ad-116">Если вам нужно использовать постоянный чат, вы можете либо перенести пользователей, требующих этой функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="160ad-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="160ad-117">Средство планирования также добавляет зеркальную SQL базы данных для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="160ad-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="160ad-118">Например, если имеется база данных SQL Server переднего плана, средство планирования добавит другую базу данных в качестве зеркальной базы данных для этой базы данных и назовет ее как "переднее SQL базы данных.</span><span class="sxs-lookup"><span data-stu-id="160ad-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="160ad-119">Дополнительные сведения о подготовке среды к высокой доступности см. в материале [Plan for high availability and disaster recovery in Skype for Business Server.](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="160ad-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
