---
title: Добавление пула директоров
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Чтобы определить полное доменное имя пула, выберите один из нескольких, который будет состоять из двух или более директоров в пуле с балансировкой нагрузки или один пул компьютеров. Кроме того, необходимо ввести полное доменное имя (FQDN), которое будет использоваться для подключения к каталогу пула или доменному имени одного из каталогов. Для пула компьютеров с режиссерами это может быть DNS-запись для виртуального IP-адреса аппаратной подсистемы балансировки нагрузки или общего DNS-записи для балансировки нагрузки DNS.
ms.openlocfilehash: 150975cedf09c19acac1afffab25f5becf053fe3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698574"
---
# <a name="add-director-pool"></a><span data-ttu-id="9225d-105">Добавление пула директоров</span><span class="sxs-lookup"><span data-stu-id="9225d-105">Add Director Pool</span></span>
 
<span data-ttu-id="9225d-106">Чтобы **определить полное доменное имя пула**, выберите один из **нескольких** , который будет состоять из двух или более директоров в пуле с балансировкой нагрузки или **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="9225d-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="9225d-107">Кроме того, необходимо ввести полное доменное имя (FQDN), которое будет использоваться для подключения к каталогу пула или доменному имени одного из каталогов.</span><span class="sxs-lookup"><span data-stu-id="9225d-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="9225d-108">Для пула компьютеров с режиссерами это может быть DNS-запись для виртуального IP-адреса аппаратной подсистемы балансировки нагрузки или общего DNS-записи для балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="9225d-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="9225d-109">Если вы планируете реализовать пул каталогов в будущем, выберите пункт **несколько пулов компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="9225d-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="9225d-110">Несмотря на то, что пул определен как два или более компьютеров, для которых настроена балансировка нагрузки, вы можете создать один пул компьютеров и создать полное доменное имя пула для одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="9225d-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="9225d-111">Когда вы будете готовы добавить другие компьютеры в пул позже, необходимо запустить построитель топологии еще раз, чтобы определить нового участника пула, опубликовать новую топологию, а затем настроить новый участник пула с помощью мастера развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9225d-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="9225d-112">Кроме того, необходимо добавить нового участника пула в соответствующие подсистемы балансировки нагрузки для пула (для балансировки нагрузки DNS) или для подсистемы балансировки нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="9225d-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="9225d-113">Во многих случаях на вашем компьютере будут установлены обе системы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="9225d-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="9225d-114">Убедитесь, что вы добавляете нового сервера участника в оба.</span><span class="sxs-lookup"><span data-stu-id="9225d-114">Be sure that you are adding the new member server to both.</span></span> 
  

