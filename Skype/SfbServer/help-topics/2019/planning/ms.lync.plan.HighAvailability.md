---
title: Высокая доступность (средство планирования)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Схема основной высокой доступности для большинства ролей сервера в Скайп для Business Server 2015 основано на избыточности сервера с помощью пула. В случае сбоя сервера, на котором выполняется определенная роль сервера, другие серверы в пуле с той же ролью берут его нагрузку на себя.
ms.openlocfilehash: cd8861177f066030e71edf5cc62b891b863b2abb
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="0f1a6-104">Высокая доступность (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="0f1a6-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="0f1a6-105">Схема основной высокой доступности для большинства ролей сервера в Скайп для Business Server 2015 основано на избыточности сервера с помощью пула.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="0f1a6-106">В случае сбоя сервера, на котором выполняется определенная роль сервера, другие серверы в пуле с той же ролью берут его нагрузку на себя.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="0f1a6-107">Скайп для Business Server 2015 требуется по крайней мере два сервера переднего плана для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="0f1a6-108">Средство планирования используются следующие критерии для определения, если будет добавлена дополнительных серверов для поддержки высокой доступности:</span><span class="sxs-lookup"><span data-stu-id="0f1a6-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="0f1a6-109">Если развертывание содержит два или более серверов переднего плана, средство планирования не добавляйте дополнительных серверов.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="0f1a6-110">Если развертывание содержит пограничного сервера, добавляется дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="0f1a6-111">Если развертывание содержит Persistent Chat, средство планирования будет добавить дополнительный сервер, но не увеличить число пула.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="0f1a6-112">К примеру Если развертывание уже содержит четырех серверов, средство планирования предложит добавления второго сервера (для всего из пяти серверов), но будет поддерживать один пул.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="0f1a6-113">Средство планирования также добавляет зеркальной базы данных SQL для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="0f1a6-114">Например если базы данных SQL сервера переднего плана, средство планирования будет добавьте другие базы данных как зеркальной базы данных на этом и назовите его как «переднего плана зеркальной базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="0f1a6-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="0f1a6-115">Дополнительные сведения о подготовке среды для обеспечения высокой доступности в разделе [Планирование высокой доступности и аварийного восстановления в Скайп для Business Server 2015](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0f1a6-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

