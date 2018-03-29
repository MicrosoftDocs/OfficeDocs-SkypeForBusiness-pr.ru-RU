---
title: Применение исправления или обновления к серверам переднего плана в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Сводка: Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a><span data-ttu-id="f6f85-103">Применение исправления или обновления к серверам переднего плана в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6f85-103">Patch or update Front End Servers in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f6f85-104">**Сводка:** Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6f85-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="f6f85-105">Исправление серверы в пуле переднего плана, происходит так на одном сервере за раз.</span><span class="sxs-lookup"><span data-stu-id="f6f85-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="f6f85-106">Установка обновления на серверы переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="f6f85-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="f6f85-107">Введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f6f85-107">Type the following cmdlet:</span></span>
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     <span data-ttu-id="f6f85-108">Если при выполнении этого командлета отображаются сведения об отсутствующих репликах, перед применением исправлений выполните следующий командлет для восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="f6f85-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. <span data-ttu-id="f6f85-109">На первом сервере, где требуется внести исправления, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f6f85-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="f6f85-110">Этот командлет перемещает все службы в других серверов переднего плана в пуле и переводит этот сервер в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="f6f85-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="f6f85-111">Примените к серверу обновление или исправление.</span><span class="sxs-lookup"><span data-stu-id="f6f85-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="f6f85-112">На обновленном сервере выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f6f85-112">On the upgraded server, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="f6f85-113">Сервер возвращается в режим нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="f6f85-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="f6f85-114">Повторите шаги 2–4 для каждого сервера, требующего обновления.</span><span class="sxs-lookup"><span data-stu-id="f6f85-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

