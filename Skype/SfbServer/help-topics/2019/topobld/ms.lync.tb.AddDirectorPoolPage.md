---
title: Добавление пула директоров
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы определить полное доменное имя пула директоров, выберите пул с несколькими компьютерами, состоящий из двух и более директоров в пуле с балансировкой нагрузки, или пул из одного компьютера. Кроме того, необходимо ввести полное доменное имя, которое будет использоваться для подключения к пулу директоров или к полному доменному имени одного директора. Для пула директоров этим именем будет DNS-запись для виртуального IP-адреса аппаратного балансировщика нагрузки или общая DNS-запись для балансировки нагрузки DNS.
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807759"
---
# <a name="add-director-pool"></a><span data-ttu-id="edbc4-105">Добавление пула директоров</span><span class="sxs-lookup"><span data-stu-id="edbc4-105">Add Director Pool</span></span>
 
<span data-ttu-id="edbc4-106">Чтобы **определить полное доменное имя пула директоров**, выберите **пул с несколькими компьютерами**, состоящий из двух и более директоров в пуле с балансировкой нагрузки, или **пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="edbc4-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="edbc4-107">Кроме того, необходимо ввести полное доменное имя, которое будет использоваться для подключения к пулу директоров или к полному доменному имени одного директора.</span><span class="sxs-lookup"><span data-stu-id="edbc4-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="edbc4-108">Для пула директоров этим именем будет DNS-запись для виртуального IP-адреса аппаратного балансировщика нагрузки или общая DNS-запись для балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="edbc4-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="edbc4-109">Если в дальнейшем планируется внедрить пул директоров, выберите **Пул с несколькими компьютерами**.</span><span class="sxs-lookup"><span data-stu-id="edbc4-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="edbc4-110">Несмотря на то, что пул является группой компьютеров с балансировкой нагрузки, можно создать пул, состоящий из одного компьютера, а затем присвоить полное доменное имя этому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="edbc4-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="edbc4-111">Когда вы будете готовы добавить дополнительные компьютеры в пул позже, необходимо снова запустить построитель топологий, чтобы определить нового участника пула, опубликовать новую топологию, а затем настроить новый член пула директоров с помощью мастера развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="edbc4-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="edbc4-112">Необходимо также добавить этого нового участника пула в соответствующие балансировщики нагрузки пула: балансировка нагрузки DNS или аппаратные средства балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="edbc4-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="edbc4-113">Во многих случаях необходимо задействовать обе системы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="edbc4-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="edbc4-114">Обязательно добавьте новый сервер участника в оба средства балансировки.</span><span class="sxs-lookup"><span data-stu-id="edbc4-114">Be sure that you are adding the new member server to both.</span></span> 
  

