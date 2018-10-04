---
title: Исправление или обновление серверов переднего плана в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Сводка: Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371719"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="1c9f2-103">Исправление или обновление серверов переднего плана в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="1c9f2-103">Patch or update Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="1c9f2-104">**Сводка:** Узнайте, как для применения исправлений и обновлений для сервера переднего плана в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="1c9f2-105">Исправление серверы в пуле переднего плана, происходит так на одном сервере за раз.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="1c9f2-106">Установка обновления на серверы переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="1c9f2-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="1c9f2-107">Введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1c9f2-107">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="1c9f2-108">Если при выполнении этого командлета отображаются сведения об отсутствующих репликах, перед применением исправлений выполните следующий командлет для восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="1c9f2-109">На первом сервере, где требуется внести исправления, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1c9f2-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="1c9f2-110">Этот командлет перемещает все службы в других серверов переднего плана в пуле и переводит этот сервер в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="1c9f2-111">Примените к серверу обновление или исправление.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="1c9f2-112">На обновленном сервере выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1c9f2-112">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="1c9f2-113">Сервер возвращается в режим нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="1c9f2-114">Повторите шаги 2–4 для каждого сервера, требующего обновления.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

