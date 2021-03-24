---
title: Управление серверами переднего конца в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Сводка. Сведения о добавлении, удалите, заплатите или обновите серверы переднего входа в Skype для бизнеса Server.
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103195"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="e6295-103">Управление серверами переднего конца в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e6295-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="e6295-104">В этой статье рассказывается о том, как добавлять или удалять серверы переднего конца и как применять обновления или исправления к передним конечным серверам.</span><span class="sxs-lookup"><span data-stu-id="e6295-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="e6295-105">Skype for Business Server 2019 не поддерживает пулы корпоративных выпусков с двумя серверами переднего входа и не позволяет публиковать топологию в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e6295-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="e6295-106">Добавление или удаление серверов переднего конца</span><span class="sxs-lookup"><span data-stu-id="e6295-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="e6295-107">Когда вы добавляете в пул или удаляете из пула сервер переднего плана, вам необходимо перезапустить пул.</span><span class="sxs-lookup"><span data-stu-id="e6295-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e6295-108">Если добавить или удалить сервер в пул в топологии, а затем опубликовать обновленную топологию, это приведет к одновременной перезагрузке всех серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="e6295-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="e6295-109">В то время как серверы перезапуска пула находится в автономном режиме, что будет прерывать службу для пользователей, подключенных к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="e6295-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="e6295-110">Чтобы предотвратить прерывание службы для пользователей, запланируйте публикацию топологии с новым сервером в пуле в не-бизнес-часы.</span><span class="sxs-lookup"><span data-stu-id="e6295-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="e6295-111">При добавлении или удалении переднего сервера можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="e6295-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6295-112">Если вы добавляете новые серверы в пул, обновите новые серверы пула, чтобы они были на том же уровне накопительного обновления, что и существующие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="e6295-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="e6295-113">Добавление или удаление серверов переднего конца</span><span class="sxs-lookup"><span data-stu-id="e6295-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="e6295-p102">Если вы удаляете серверы переднего плана, сначала запретите новые подключения к ним. Для этого вы можете использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e6295-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="e6295-116">Откройте построитель топологий и добавьте или удалите требуемые серверы.</span><span class="sxs-lookup"><span data-stu-id="e6295-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="e6295-117">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="e6295-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6295-118">Если добавить или удалить сервер в пул в топологии, а затем опубликовать обновленную топологию, это приведет к одновременной перезагрузке всех серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="e6295-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="e6295-119">В то время как серверы перезапуска пула находится в автономном режиме, что будет прерывать службу для пользователей, подключенных к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="e6295-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="e6295-120">Чтобы предотвратить прерывание службы для пользователей, запланируйте публикацию топологии с новым сервером в пуле в не-бизнес-часы.</span><span class="sxs-lookup"><span data-stu-id="e6295-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="e6295-121">Кроме того, при добавлении или удалении сервера в пул необходимо запустить мастер развертывания Skype для бизнеса на каждом добавленном или удаленном компьютере, дополнительные сведения см. в статьи [Установка Skype для](../../deploy/install/install-skype-for-business-server.md) бизнеса Server на серверах топологии</span><span class="sxs-lookup"><span data-stu-id="e6295-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)</span></span>
  
4. <span data-ttu-id="e6295-122">Если вы изменили количество серверов в пуле передней части любым из следующих способов, сбросите пул, введя следующий cmdlet: Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="e6295-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="e6295-123">2 к любому</span><span class="sxs-lookup"><span data-stu-id="e6295-123">2 to any</span></span>
    
     - <span data-ttu-id="e6295-124">Любое до 2</span><span class="sxs-lookup"><span data-stu-id="e6295-124">Any to 2</span></span>
    
     - <span data-ttu-id="e6295-125">3 к любому</span><span class="sxs-lookup"><span data-stu-id="e6295-125">3 to any</span></span>
    
     - <span data-ttu-id="e6295-126">Любое до 3</span><span class="sxs-lookup"><span data-stu-id="e6295-126">Any to 3</span></span>
    
5. <span data-ttu-id="e6295-127">Перезапустите пул, введя следующий кодлет</span><span class="sxs-lookup"><span data-stu-id="e6295-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="e6295-128">Исправление или обновление серверов переднего конца</span><span class="sxs-lookup"><span data-stu-id="e6295-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="e6295-129">При исправлении серверов в пуле переднего конца вы делаете это по одному серверу одновременно.</span><span class="sxs-lookup"><span data-stu-id="e6295-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="e6295-130">Применение обновления для серверов переднего конца в пуле</span><span class="sxs-lookup"><span data-stu-id="e6295-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="e6295-131">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e6295-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="e6295-132">Если в этом комлете показаны отсутствующие реплики, запустите следующий кодлет, чтобы восстановить пул, прежде чем применять какие-либо исправления.</span><span class="sxs-lookup"><span data-stu-id="e6295-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="e6295-133">На первом сервере, который требуется выполнить исправление, запустите следующий кодлет:</span><span class="sxs-lookup"><span data-stu-id="e6295-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="e6295-134">Этот комлет перемещает все службы на другие серверы переднего конечного доступа в пуле и отвоевает этот сервер в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="e6295-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="e6295-135">Применить обновление или исправление на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="e6295-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="e6295-136">На обновленном сервере запустите следующий кодлет:</span><span class="sxs-lookup"><span data-stu-id="e6295-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="e6295-137">Сервер возвращается в службу.</span><span class="sxs-lookup"><span data-stu-id="e6295-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="e6295-138">Повторите действия 2-4 для каждого сервера, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="e6295-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
