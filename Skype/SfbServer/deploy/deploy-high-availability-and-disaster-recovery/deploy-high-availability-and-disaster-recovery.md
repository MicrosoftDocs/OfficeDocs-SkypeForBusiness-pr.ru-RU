---
title: Развертывание функций высокой доступности и аварийного восстановления
ms.author: heidip
author: microsoftheidi
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 'Skype для бизнеса Server предоставляет высокую доступность с объединением серверов, аварийное восстановление с сопряжением пулов и несколько режимов высокой доступности внутреннего сервера, включая группы доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивая кластеризация для SQL. '
ms.openlocfilehash: 91324a4bbc0c6a2439a3190661320165670a6e11
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="9c40c-103">Развертывание функций высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="9c40c-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="9c40c-104">Skype для бизнеса Server предоставляет высокую доступность с объединением серверов, аварийное восстановление с сопряжением пулов и несколько режимов высокой доступности внутреннего сервера, включая группы доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивая кластеризация для SQL. </span><span class="sxs-lookup"><span data-stu-id="9c40c-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availibility, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="9c40c-105">Высокая доступность относится к проверке того, что Скайп для служб Business Server доступны даже в том случае, если один или несколько серверов, тем ниже. Аварийное восстановление охватывает службы хранения переход в случае аварии природные или отдела, возникающие и сохранения данных из до аварии по мере возможности.</span><span class="sxs-lookup"><span data-stu-id="9c40c-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="9c40c-106">В этом разделе рассматривается развертывание этих компонентов, а также процедуры по настройке высокой доступности и аварийного восстановления для остальных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="9c40c-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="9c40c-107">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9c40c-107">Related sections</span></span>

[<span data-ttu-id="9c40c-108">Планирование высокой доступности и аварийного восстановления в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c40c-108">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="9c40c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9c40c-109">See also</span></span>

#### 

[<span data-ttu-id="9c40c-110">Развертывание группы обеспечения доступности AlwaysOn на сервере заднего плана в Скайп for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c40c-110">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="9c40c-111">Развертывание парных пулов переднего плана для аварийного восстановления в Скайп for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c40c-111">Deploy paired Front End pools for disaster recovery in Skype for Business Server 2015</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="9c40c-112">Развертывание зеркального отображения SQL для обеспечения высокой доступности Тыловой сервер в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c40c-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
[<span data-ttu-id="9c40c-113">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c40c-113">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

