---
title: Добавление полного доменного имени интерфейсного пула
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Укажите полное доменное имя создаваемого интерфейсного пула. Невозможно изменить полное доменное имя пула после публикации топологии, содержащей интерфейсный пул. Если необходимо переименовать пул, следует удалить пул, а затем добавить новый пул с новым полным доменным именем.
ms.openlocfilehash: 7b0b14ab9b8cb450a80872cedf61e6f24da91dc2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811659"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="57a2e-105">Добавление полного доменного имени интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="57a2e-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="57a2e-p102">Укажите полное доменное имя создаваемого интерфейсного пула. Невозможно изменить полное доменное имя пула после публикации топологии, содержащей интерфейсный пул. Если необходимо переименовать пул, следует удалить пул, а затем добавить новый пул с новым полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="57a2e-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="57a2e-109">Если в дальнейшем планируется внедрить интерфейсный пул, выберите **Пул с несколькими компьютерами**.</span><span class="sxs-lookup"><span data-stu-id="57a2e-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="57a2e-110">Несмотря на то, что пул является группой компьютеров с балансировкой нагрузки, можно создать пул, состоящий из одного компьютера, а затем присвоить полное доменное имя этому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="57a2e-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="57a2e-111">Когда вы будете готовы добавить дополнительные компьютеры в пул позже, необходимо снова запустить построитель топологий, чтобы определить нового участника пула, опубликовать новую топологию, а затем настроить новый член пула переднего сервера с помощью мастера развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="57a2e-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="57a2e-112">Необходимо также добавить этого нового участника пула в соответствующие балансировщики нагрузки пула: балансировка нагрузки DNS или аппаратные средства балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="57a2e-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="57a2e-113">Во многих случаях необходимо задействовать обе системы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="57a2e-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="57a2e-114">Обязательно добавьте новый сервер участника в оба средства балансировки.</span><span class="sxs-lookup"><span data-stu-id="57a2e-114">Be sure that you are adding the new member server to both.</span></span> 
  

