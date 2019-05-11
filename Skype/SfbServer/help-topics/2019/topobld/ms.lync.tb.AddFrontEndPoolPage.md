---
title: Добавление полного доменного имени пула переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Укажите полное доменное имя (FQDN) пула переднего плана, для которого создается. Полное доменное имя пула нельзя изменить после публикации топологии, содержащий пула переднего плана. Если требуется переименовать в пул, необходимо удалить пул и добавьте новый пул с новой полным доменным ИМЕНЕМ.
ms.openlocfilehash: f11d45c881053298374f92f692b623f5cee2e183
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888998"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="412e6-105">Добавление полного доменного имени пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="412e6-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="412e6-106">Укажите полное доменное имя (FQDN) пула переднего плана, для которого создается.</span><span class="sxs-lookup"><span data-stu-id="412e6-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="412e6-107">Полное доменное имя пула нельзя изменить после публикации топологии, содержащий пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="412e6-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="412e6-108">Если требуется переименовать в пул, необходимо удалить пул и добавьте новый пул с новой полным доменным ИМЕНЕМ.</span><span class="sxs-lookup"><span data-stu-id="412e6-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="412e6-109">Если планируется реализовать пула переднего плана в будущем, выберите **пул на нескольких компьютерах**.</span><span class="sxs-lookup"><span data-stu-id="412e6-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="412e6-110">Хотя пул определяется как несколько компьютеров с балансировкой нагрузки, можно создать пул из одного компьютера и присвоить этому компьютеру полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="412e6-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="412e6-111">Когда вы готовы к Добавление компьютеров в пуле более поздней версии, необходимо запустить построитель топологий еще раз, чтобы определить новый элемент пула, публикации новой топологии и затем настроить новый элемент пула переднего плана через Скайп мастер развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="412e6-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="412e6-112">Необходимо также добавить новый элемент пула подсистемы балансировки нагрузки соответствующие для пула, балансировка нагрузки доменных имен (DNS) или аппаратных балансировщиков нагрузки.</span><span class="sxs-lookup"><span data-stu-id="412e6-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="412e6-113">Во многих случаях бы обеих систем на месте балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="412e6-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="412e6-114">Не забудьте, добавляется новый сервер участника к обоим.</span><span class="sxs-lookup"><span data-stu-id="412e6-114">Be sure that you are adding the new member server to both.</span></span> 
  

