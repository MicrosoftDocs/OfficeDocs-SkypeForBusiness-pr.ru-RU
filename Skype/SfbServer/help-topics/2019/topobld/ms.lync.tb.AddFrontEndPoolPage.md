---
title: Добавление полного доменного имени пула переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Укажите полное доменное имя (FQDN) для пула переднего плана, который вы хотите создать. После публикации топологии с интерфейсом переднего плана вы не можете изменить полное доменное имя пула в пуле. Если вам нужно переименовать пул, необходимо удалить пул и добавить новый пул с новым полным доменным именем.
ms.openlocfilehash: 00bc6276062412abe55a518a45941fa9c4fbaff8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297753"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="f0059-105">Добавление полного доменного имени пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="f0059-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="f0059-106">Укажите полное доменное имя (FQDN) для пула переднего плана, который вы хотите создать.</span><span class="sxs-lookup"><span data-stu-id="f0059-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="f0059-107">После публикации топологии с интерфейсом переднего плана вы не можете изменить полное доменное имя пула в пуле.</span><span class="sxs-lookup"><span data-stu-id="f0059-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="f0059-108">Если вам нужно переименовать пул, необходимо удалить пул и добавить новый пул с новым полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="f0059-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="f0059-109">Если вы планируете реализовать интерфейсную группу переднего плана в будущем, выберите **несколько пулов компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="f0059-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f0059-110">Хотя пул определяется как несколько компьютеров с балансировкой нагрузки, можно создать пул из одного компьютера и присвоить этому компьютеру полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="f0059-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f0059-111">Когда вы будете готовы добавить другие компьютеры в пул позже, необходимо запустить построитель топологии еще раз, чтобы определить нового участника пула, опубликовать новую топологию и настроить новый участник пула с помощью мастера развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f0059-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f0059-112">Кроме того, необходимо добавить нового участника пула в соответствующие подсистемы балансировки нагрузки для пула, балансировки нагрузки службы доменных имен (DNS) или подсистем балансировки нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="f0059-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="f0059-113">Во многих случаях вы должны иметь обе системы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f0059-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="f0059-114">Убедитесь, что вы добавляете нового сервера участника в оба.</span><span class="sxs-lookup"><span data-stu-id="f0059-114">Be sure that you are adding the new member server to both.</span></span> 
  

