---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Основная схема высокой доступности для большинства ролей сервера в Skype для бизнеса Server 2015 базируется на избыточности сервера посредством группировки. В случае сбоя сервера, на котором выполняется определенная роль сервера, другие серверы в пуле с той же ролью берут его нагрузку на себя.
ms.openlocfilehash: 740c12439683fcefccaef11358a8cb65a4fae65a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281089"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="a4a0b-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="a4a0b-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="a4a0b-105">Основная схема высокой доступности для большинства ролей сервера в Skype для бизнеса Server 2015 базируется на избыточности сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a4a0b-106">В случае сбоя сервера, на котором выполняется определенная роль сервера, другие серверы в пуле с той же ролью берут его нагрузку на себя.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="a4a0b-107">Для обеспечения высокой доступности в Skype для бизнеса Server 2015 требуется по крайней мере два сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="a4a0b-108">В средстве планирования используются следующие условия, чтобы определить, добавляются ли дополнительные серверы для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="a4a0b-109">Если развертывание содержит два или более серверов переднего плана, средство планирования не добавляет дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="a4a0b-110">Если развертывание содержит пограничный сервер, добавляется дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="a4a0b-111">Если в развертывании есть сохраняемый чат, средство планирования добавит дополнительный сервер, но не увеличит номер пула.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="a4a0b-112">Например, если в развертывании уже есть четыре сервера, средство планирования предложит добавить дополнительный сервер (для всего пяти серверов), но будет поддерживать один пул.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="a4a0b-113">Средство планирования также добавляет зеркальную базу данных SQL для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="a4a0b-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="a4a0b-114">Например, если у вас есть клиентская база данных SQL Server, средство планирования добавит другую базу данных в качестве зеркальной базы данных для этого файла и присвойте ей имя в качестве «серверной базы данных SQL переднего плана».</span><span class="sxs-lookup"><span data-stu-id="a4a0b-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="a4a0b-115">Дополнительные сведения о подготовке среды к высокой доступности можно найти в разделе [Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a4a0b-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

