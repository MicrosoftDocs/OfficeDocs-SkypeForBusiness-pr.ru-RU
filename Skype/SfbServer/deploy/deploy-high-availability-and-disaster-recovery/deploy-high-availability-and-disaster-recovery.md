---
title: Развертывание функций высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.
ms.openlocfilehash: cb4d39df7f6a12a14c25533d8c6fb1ae95da24d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240066"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="11cb6-103">Развертывание функций высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="11cb6-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="11cb6-104">Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.</span><span class="sxs-lookup"><span data-stu-id="11cb6-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="11cb6-105">Высокий уровень доступности — это обеспечение доступности служб Skype для бизнеса Server даже в том случае, если один или несколько серверов отключаются. Аварийное восстановление — это использование служб, которые применяют к возникновению серьезных или человеческих ситуаций, и сохраняет как можно большие данные до аварии.</span><span class="sxs-lookup"><span data-stu-id="11cb6-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="11cb6-106">В этом разделе рассматривается развертывание этих компонентов, а также процедуры по настройке высокой доступности и аварийного восстановления для остальных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="11cb6-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="11cb6-107">Зеркальное отображение SQL доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="11cb6-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="11cb6-108">Группы доступности AlwaysOn, экземпляры отказоустойчивого кластера AlwaysOn (FCI) и методы отказоустойчивой кластеризации SQL являются предпочтительными в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="11cb6-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="11cb6-109">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="11cb6-109">Related sections</span></span>

[<span data-ttu-id="11cb6-110">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="11cb6-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="11cb6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="11cb6-111">See also</span></span>

[<span data-ttu-id="11cb6-112">Развертывание группы доступности AlwaysOn на обратном стороне сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="11cb6-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="11cb6-113">Развертывание попарных пулов переднего плана для аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="11cb6-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="11cb6-114">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="11cb6-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
