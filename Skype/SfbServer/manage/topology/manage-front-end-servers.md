---
title: Управление серверами переднего плана в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Сводка. Узнайте, как добавить, удалить, исправить или обновить серверы переднего плана в Skype для бизнеса Server.
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098417"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="4551d-103">Управление серверами переднего плана в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4551d-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="4551d-104">В этой статье объясняется, как добавить или удалить серверы переднего плана, а также как применять обновления или исправления к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4551d-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="4551d-105">Skype для бизнеса Server 2019 не поддерживает пулы переднего плана Enterprise Edition с двумя серверами переднего плана и не разрешают публикацию топологии в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="4551d-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="4551d-106">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="4551d-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="4551d-107">Когда вы добавляете в пул или удаляете из пула сервер переднего плана, вам необходимо перезапустить пул.</span><span class="sxs-lookup"><span data-stu-id="4551d-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4551d-108">Когда вы добавляете или удаляете сервер в пуле в топологии и затем публикуете обновленную топологию, все серверы в пуле будут перезапускаться в то же время.</span><span class="sxs-lookup"><span data-stu-id="4551d-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="4551d-109">Серверы перезапускают пул в автономном режиме, что приведет к прерыванию службы для пользователей, подключенных к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="4551d-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="4551d-110">Чтобы предотвратить прерывание обслуживания для пользователей, запланируйте публикацию топологии с новым сервером в пуле в нерабочие часы.</span><span class="sxs-lookup"><span data-stu-id="4551d-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="4551d-111">При добавлении или удалении сервера переднего плана можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="4551d-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4551d-112">Если вы добавляете в пул новые серверы, обновите новые серверы пула так, чтобы они были на том же накопительном уровне обновления, что и существующие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="4551d-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="4551d-113">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="4551d-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="4551d-p102">Если вы удаляете серверы переднего плана, сначала запретите новые подключения к ним. Для этого вы можете использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4551d-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="4551d-116">Откройте построитель топологий и добавьте или удалите требуемые серверы.</span><span class="sxs-lookup"><span data-stu-id="4551d-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="4551d-117">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="4551d-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4551d-118">Когда вы добавляете или удаляете сервер в пуле в топологии и затем публикуете обновленную топологию, все серверы в пуле будут перезапускаться в то же время.</span><span class="sxs-lookup"><span data-stu-id="4551d-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="4551d-119">Серверы перезапускают пул в автономном режиме, что приведет к прерыванию службы для пользователей, подключенных к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="4551d-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="4551d-120">Чтобы предотвратить прерывание обслуживания для пользователей, запланируйте публикацию топологии с новым сервером в пуле в нерабочие часы.</span><span class="sxs-lookup"><span data-stu-id="4551d-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="4551d-121">Кроме того, при добавлении или удалении сервера в пул необходимо запустить мастер развертывания Skype для бизнеса Server на каждом добавленном или удаленном компьютере, чтобы получить дополнительные сведения, [в статье Установка Skype для бизнеса Server на серверах в топологии](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="4551d-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="4551d-122">Если количество серверов в пуле переднего плана было изменено одним из следующих способов, выполните сброс пула с помощью следующего командлета: Reset — Кспулрегистрарстате — ResetType FullReset – PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="4551d-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="4551d-123">2 для любого</span><span class="sxs-lookup"><span data-stu-id="4551d-123">2 to any</span></span>
    
     - <span data-ttu-id="4551d-124">Любое значение, равное 2</span><span class="sxs-lookup"><span data-stu-id="4551d-124">Any to 2</span></span>
    
     - <span data-ttu-id="4551d-125">3 до любого</span><span class="sxs-lookup"><span data-stu-id="4551d-125">3 to any</span></span>
    
     - <span data-ttu-id="4551d-126">Любое значение 3</span><span class="sxs-lookup"><span data-stu-id="4551d-126">Any to 3</span></span>
    
5. <span data-ttu-id="4551d-127">Перезапустите пул, введя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4551d-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="4551d-128">Обновление или обновление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="4551d-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="4551d-129">При обновлении серверов в интерфейсном пуле вы выполняете по одному серверу за раз.</span><span class="sxs-lookup"><span data-stu-id="4551d-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="4551d-130">Применение обновления к серверам переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="4551d-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="4551d-131">Введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4551d-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="4551d-132">Если этот командлет отображает все отсутствующие реплики, выполните следующий командлет для восстановления пула перед применением исправлений.</span><span class="sxs-lookup"><span data-stu-id="4551d-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="4551d-133">На первом сервере, который требуется исправить, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4551d-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="4551d-134">Этот командлет переместит все службы на другие серверы переднего плана в пуле и переводит этот сервер в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="4551d-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="4551d-135">Примените обновление или исправление к этому серверу.</span><span class="sxs-lookup"><span data-stu-id="4551d-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="4551d-136">На обновленном сервере выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4551d-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="4551d-137">Сервер возвращается в службу.</span><span class="sxs-lookup"><span data-stu-id="4551d-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="4551d-138">Повторите шаги 2-4 для каждого сервера, который требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="4551d-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
