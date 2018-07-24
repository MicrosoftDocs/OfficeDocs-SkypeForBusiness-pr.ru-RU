---
title: Добавление или удаление сервера переднего плана в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Сводка: Узнайте, как добавление и удаление серверов переднего плана в Скайп для Business Server.'
ms.openlocfilehash: 07f23f3dfb913a353a72ac855915d4001ed02f24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018785"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server"></a><span data-ttu-id="94aa0-103">Добавление или удаление сервера переднего плана в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="94aa0-103">Add or remove a Front End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="94aa0-104">**Сводка:** Узнайте, как добавление и удаление серверов переднего плана в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="94aa0-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="94aa0-105">При добавлении сервера переднего плана в пул, или удаление сервера переднего плана из пула, необходимо перезапустить пул.</span><span class="sxs-lookup"><span data-stu-id="94aa0-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="94aa0-p101">При добавлении или удалении сервера из пула в топологии и последующей публикации измененной топологии все серверы в пуле будут перезагружены одновременно. В течение перезагрузки пул остается недоступным для подключенных к нему пользователей. Чтобы предотвратить перерыв в обслуживании, публикацию топологии с новым сервером в пуле необходимо запланировать на период за пределами рабочего времени.</span><span class="sxs-lookup"><span data-stu-id="94aa0-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="94aa0-109">Можно использовать следующую процедуру при добавлении или удалении сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="94aa0-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94aa0-110">При добавлении в пул новых серверов их уровень накопительного пакета обновления должен быть таким же, как у существующих серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="94aa0-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="94aa0-111">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="94aa0-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="94aa0-112">Для удаления любого сервера переднего плана, сначала остановите все новые подключения к серверам.</span><span class="sxs-lookup"><span data-stu-id="94aa0-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="94aa0-113">Для этого вы можете использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="94aa0-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="94aa0-114">Откройте построитель топологий и добавьте или удалите требуемые серверы.</span><span class="sxs-lookup"><span data-stu-id="94aa0-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="94aa0-115">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="94aa0-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94aa0-p103">При добавлении или удалении сервера из пула в топологии и последующей публикации измененной топологии все серверы в пуле будут перезагружены одновременно. В течение перезагрузки пул остается недоступным для подключенных к нему пользователей. Чтобы предотвратить перерыв в обслуживании, публикацию топологии с новым сервером в пуле необходимо запланировать на период за пределами рабочего времени.</span><span class="sxs-lookup"><span data-stu-id="94aa0-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="94aa0-119">При изменении числа серверов в пуле переднего плана в любом из указанных ниже способов, затем перезапустите пул с, введя следующий командлет: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="94aa0-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="94aa0-120">2 — любое количество</span><span class="sxs-lookup"><span data-stu-id="94aa0-120">2 to any</span></span>
    
     - <span data-ttu-id="94aa0-121">Любое количество — 2</span><span class="sxs-lookup"><span data-stu-id="94aa0-121">Any to 2</span></span>
    
     - <span data-ttu-id="94aa0-122">3 — любое количество</span><span class="sxs-lookup"><span data-stu-id="94aa0-122">3 to any</span></span>
    
     - <span data-ttu-id="94aa0-123">Любое количество — 3</span><span class="sxs-lookup"><span data-stu-id="94aa0-123">Any to 3</span></span>
    
5. <span data-ttu-id="94aa0-124">Перезапустите пул с помощью следующего командлета</span><span class="sxs-lookup"><span data-stu-id="94aa0-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```