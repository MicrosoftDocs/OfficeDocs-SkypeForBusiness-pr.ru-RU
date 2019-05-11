---
title: Развертывание функций высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.
ms.openlocfilehash: 96e1f0614aac72197f0b34b8432b65d2c859c4ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894593"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="897a7-103">Развертывание функций высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="897a7-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="897a7-104">Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.</span><span class="sxs-lookup"><span data-stu-id="897a7-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="897a7-105">Высокая доступность относится к проверке того, что Скайп для служб Business Server доступны даже в том случае, если один или несколько серверов, тем ниже. Аварийное восстановление охватывает службы хранения переход в случае аварии природные или отдела, возникающие и сохранения данных из до аварии по мере возможности.</span><span class="sxs-lookup"><span data-stu-id="897a7-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="897a7-106">В этом разделе рассматривается развертывание этих компонентов, а также процедуры по настройке высокой доступности и аварийного восстановления для остальных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="897a7-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="897a7-107">Зеркальное отображение SQL доступна в Скайп для Business Server 2015, но в Скайп Business Server 2019 больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="897a7-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="897a7-108">Методы кластеризации отработки отказа группы обеспечения доступности AlwaysOn, экземпляры кластера AlwaysOn отработки отказа (FCI) и SQL, являются предпочтительными с Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="897a7-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="897a7-109">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="897a7-109">Related sections</span></span>

[<span data-ttu-id="897a7-110">Планирование высокой доступности и аварийного восстановления в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="897a7-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="897a7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="897a7-111">See also</span></span>

[<span data-ttu-id="897a7-112">Развертывание группы обеспечения доступности AlwaysOn на сервере заднего плана в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="897a7-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="897a7-113">Развертывание парных пулов переднего плана для аварийного восстановления в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="897a7-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="897a7-114">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="897a7-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
