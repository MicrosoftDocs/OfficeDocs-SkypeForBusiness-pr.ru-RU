---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Основная схема высокой доступности для большинства ролей сервера в Skype для бизнеса Server основывается на избыточности сервера посредством группировки. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.
ms.openlocfilehash: dc438d5b46f54f7526b0d1327a3263d9e334b68d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689824"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="02b77-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="02b77-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="02b77-105">Основная схема высокой доступности для большинства ролей сервера в Skype для бизнеса Server основывается на избыточности сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="02b77-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="02b77-106">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="02b77-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="02b77-107">Для обеспечения высокой доступности в Skype для бизнеса Server требуется по крайней мере два сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="02b77-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="02b77-108">В средстве планирования используются следующие условия, чтобы определить, добавляются ли дополнительные серверы для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="02b77-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="02b77-109">Если развертывание содержит два или более серверов переднего плана, средство планирования не добавляет дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="02b77-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="02b77-110">Если развертывание содержит пограничный сервер, добавляется дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="02b77-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="02b77-111">Если в развертывании есть сохраняемый чат, средство планирования добавит дополнительный сервер, но не увеличит номер пула.</span><span class="sxs-lookup"><span data-stu-id="02b77-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="02b77-112">Например, если в развертывании уже есть четыре сервера, средство планирования предложит добавить дополнительный сервер (для всего пяти серверов), но будет поддерживать один пул.</span><span class="sxs-lookup"><span data-stu-id="02b77-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="02b77-113">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="02b77-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="02b77-114">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="02b77-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="02b77-115">Дополнительные сведения можно найти [в разделе Skype для бизнеса и Microsoft Teams Upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="02b77-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="02b77-116">Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым нужны эти функции, в Teams, либо продолжить работу в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="02b77-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="02b77-117">Средство планирования также добавляет зеркальную базу данных SQL для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="02b77-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="02b77-118">Например, если у вас есть клиентская база данных SQL Server, средство планирования добавит другую базу данных в качестве зеркальной базы данных для этого файла и присвойте ей имя в качестве «серверной базы данных SQL переднего плана».</span><span class="sxs-lookup"><span data-stu-id="02b77-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="02b77-119">Дополнительные сведения о подготовке среды к высокой доступности можно найти в разделе [Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="02b77-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

