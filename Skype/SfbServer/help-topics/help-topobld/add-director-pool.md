---
title: Добавление пула директоров
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Чтобы определить полное доменное имя пула директоров, выберите пул на нескольких компьютерах, который будет состоять из двух или нескольких директоров в пуле подсистемы балансировки нагрузки или пул одиночного компьютера. Кроме того, необходимо ввести полное доменное имя (FQDN), который будет использоваться для подключения к пул директоров или полное доменное имя одного директора. Для пула директоров компьютеров это будет запись доменных имен (DNS) для виртуальный IP-адрес аппаратного балансировщика нагрузки или общей записи DNS для балансировки нагрузки DNS.
ms.openlocfilehash: 6f1e9fd873cfbd09ab8e9bc27323082be4d125a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886531"
---
# <a name="add-director-pool"></a><span data-ttu-id="f101f-105">Добавление пула директоров</span><span class="sxs-lookup"><span data-stu-id="f101f-105">Add Director Pool</span></span>
 
<span data-ttu-id="f101f-106">Чтобы **определить полное доменное имя пула директоров**выберите **пул на нескольких компьютерах** , который будет состоять из двух или нескольких директоров в пуле подсистемы балансировки нагрузки или **пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="f101f-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="f101f-107">Кроме того, необходимо ввести полное доменное имя (FQDN), который будет использоваться для подключения к пул директоров или полное доменное имя одного директора.</span><span class="sxs-lookup"><span data-stu-id="f101f-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="f101f-108">Для пула директоров компьютеров это будет запись доменных имен (DNS) для виртуальный IP-адрес аппаратного балансировщика нагрузки или общей записи DNS для балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="f101f-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="f101f-109">Если планируется реализовать пул директоров в будущем, выберите **пул на нескольких компьютерах**.</span><span class="sxs-lookup"><span data-stu-id="f101f-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f101f-110">Несмотря на то, что пула определен как два или более компьютеров, которые являются балансировку сетевой нагрузки, можно создать пул с одним компьютером и создать полное доменное имя пула для одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="f101f-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f101f-111">Когда вы готовы к Добавление компьютеров в пуле более поздней версии, необходимо запустить построитель топологий еще раз, чтобы определить новый элемент пула, публикации новой топологии и затем программы установки нового участника пула директора через Скайп для мастера развертывания сервера Business.</span><span class="sxs-lookup"><span data-stu-id="f101f-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f101f-112">Необходимо также добавить новый элемент пула подсистемы балансировки нагрузки соответствующие для пула для доменных имен (DNS) балансировки нагрузки, или для оборудования подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f101f-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="f101f-113">Во многих случаях будут иметь оба систем на месте балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f101f-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="f101f-114">Не забудьте, добавляется новый сервер участника к обоим.</span><span class="sxs-lookup"><span data-stu-id="f101f-114">Be sure that you are adding the new member server to both.</span></span> 
  

