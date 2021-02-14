---
title: Высокая доступность (средство планирования)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: Основная схема высокой доступности для большинства ролей сервера в Skype для бизнеса Server 2015 основана на избыточности серверов с помощью пулов. При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.
ms.openlocfilehash: a866784f94dd2e2c861aa93c482b40946da7ac7d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829009"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="b80df-104">Высокая доступность (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="b80df-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="b80df-105">Основная схема высокой доступности для большинства ролей сервера в Skype для бизнеса Server 2015 основана на избыточности серверов с помощью пулов.</span><span class="sxs-lookup"><span data-stu-id="b80df-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="b80df-106">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="b80df-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="b80df-107">Для обеспечения высокой доступности Skype для бизнеса Server 2015 требуется по крайней мере два сервера переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="b80df-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="b80df-108">Средство планирования использует следующие критерии, чтобы определить, будут ли добавлены дополнительные серверы для поддержки высокой доступности:</span><span class="sxs-lookup"><span data-stu-id="b80df-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="b80df-109">Если развертывание содержит два или более серверов переднего плана, средство планирования не добавляет дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="b80df-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="b80df-110">Если развертывание содержит edge Server, добавляется дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="b80df-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="b80df-111">Если развертывание содержит сохраняемого чата, средство планирования добавит дополнительный сервер, но не увеличит номер пула.</span><span class="sxs-lookup"><span data-stu-id="b80df-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="b80df-112">Например, если развертывание уже содержит четыре сервера, средство планирования предложит добавить дополнительный сервер (всего пять серверов), но будет поддерживать один пул.</span><span class="sxs-lookup"><span data-stu-id="b80df-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="b80df-113">Средство планирования также добавляет зеркальную SQL для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="b80df-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="b80df-114">Например, если имеется база данных SQL Server переднего плана, средство планирования добавит другую базу данных в качестве зеркальной базы данных для этой базы данных и назовет ее "Зеркальная база данных SQL переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b80df-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="b80df-115">Дополнительные сведения о подготовке среды для высокой доступности см. в плане высокой доступности и аварийного восстановления [в Skype для бизнеса Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="b80df-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

