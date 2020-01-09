---
title: Управление серверами переднего плана в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Сводка. сведения о том, как добавлять, удалять, исправлять и обновлять серверы переднего плана в Skype для бизнеса Server.
ms.openlocfilehash: 3689b869ba715f431ebcf0b537b4106a66177c62
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991534"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="7ccc2-103">Управление серверами переднего плана в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7ccc2-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="7ccc2-104">В этой статье объясняется, как добавить или удалить серверы переднего плана и как применять обновления или пакеты исправлений к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="7ccc2-105">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="7ccc2-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="7ccc2-106">Если вы добавите сервер переднего плана в пул или удалите сервер переднего плана из пула, необходимо перезапустить пул.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7ccc2-p101">При добавлении или удалении сервера из пула в топологии и последующей публикации измененной топологии все серверы в пуле будут перезагружены одновременно. В течение перезагрузки пул остается недоступным для подключенных к нему пользователей. Чтобы предотвратить перерыв в обслуживании, публикацию топологии с новым сервером в пуле необходимо запланировать на период за пределами рабочего времени.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="7ccc2-110">При добавлении или удалении сервера переднего плана вы можете использовать описанную ниже процедуру.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ccc2-111">При добавлении в пул новых серверов их уровень накопительного пакета обновления должен быть таким же, как у существующих серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="7ccc2-112">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="7ccc2-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="7ccc2-113">Если удаляются все серверы переднего плана, сначала необходимо остановить новые подключения к этим серверам.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="7ccc2-114">Для этого вы можете использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7ccc2-114">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="7ccc2-115">Откройте построитель топологии и добавьте или удалите необходимые серверы.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="7ccc2-116">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ccc2-p103">При добавлении или удалении сервера из пула в топологии и последующей публикации измененной топологии все серверы в пуле будут перезагружены одновременно. В течение перезагрузки пул остается недоступным для подключенных к нему пользователей. Чтобы предотвратить перерыв в обслуживании, публикацию топологии с новым сервером в пуле необходимо запланировать на период за пределами рабочего времени.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="7ccc2-120">Кроме того, при добавлении или удалении сервера в пул необходимо запустить мастер развертывания Skype для бизнеса Server на каждом удаленном компьютере, чтобы получить дополнительные сведения, в разделе [Установка сервера Skype для бизнеса на серверах в топологии](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="7ccc2-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="7ccc2-121">Если вы изменили число серверов в пуле переднего плана одним из указанных ниже способов, выполните сброс пула, введя следующий командлет: Reset-Кспулрегистрарстате-Ресеттипе Фуллресет-Пулфкдн</span><span class="sxs-lookup"><span data-stu-id="7ccc2-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="7ccc2-122">2 — любое количество</span><span class="sxs-lookup"><span data-stu-id="7ccc2-122">2 to any</span></span>
    
     - <span data-ttu-id="7ccc2-123">Любое количество — 2</span><span class="sxs-lookup"><span data-stu-id="7ccc2-123">Any to 2</span></span>
    
     - <span data-ttu-id="7ccc2-124">3 — любое количество</span><span class="sxs-lookup"><span data-stu-id="7ccc2-124">3 to any</span></span>
    
     - <span data-ttu-id="7ccc2-125">Любое количество — 3</span><span class="sxs-lookup"><span data-stu-id="7ccc2-125">Any to 3</span></span>
    
5. <span data-ttu-id="7ccc2-126">Перезапустите пул с помощью следующего командлета</span><span class="sxs-lookup"><span data-stu-id="7ccc2-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="7ccc2-127">Применение исправления или обновления к серверам переднего плана</span><span class="sxs-lookup"><span data-stu-id="7ccc2-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="7ccc2-128">После того как вы закончите обновление серверов в пуле переднего плана, вы сделайте это одним сервером за один раз.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="7ccc2-129">Установка обновления на серверы переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="7ccc2-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="7ccc2-130">Введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7ccc2-130">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="7ccc2-131">Если при выполнении этого командлета отображаются сведения об отсутствующих репликах, перед применением исправлений выполните следующий командлет для восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="7ccc2-132">На первом сервере, где требуется внести исправления, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7ccc2-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="7ccc2-133">Этот командлет перемещает все службы на другие серверы переднего плана в пуле и переводит этот сервер в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="7ccc2-134">Примените к серверу обновление или исправление.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="7ccc2-135">На обновленном сервере выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7ccc2-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="7ccc2-136">Сервер возвращается в режим нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="7ccc2-137">Повторите шаги 2–4 для каждого сервера, требующего обновления.</span><span class="sxs-lookup"><span data-stu-id="7ccc2-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
