---
title: Добавление A / V MCU пула
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Все Enterprise Edition серверов переднего плана из центрального сайта, у которых нет выровненных A / аудио-и видеоконференциями службы можно использовать одном автономного A / пула аудио-и видеоконференциями. Для каждого A аудио- и видео конференций, необходимо указать полное доменное имя (FQDN) для пула и является ли он будет иметь только один объект аудио- и видеоконференций или нескольких балансировку сетевой нагрузки A / V серверах конференц-связи.
ms.openlocfilehash: c58d2e405d642209f91e38d98d5c6cbef924cd2e
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060090"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="f3f7b-104">Добавление A / V MCU пула</span><span class="sxs-lookup"><span data-stu-id="f3f7b-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="f3f7b-105">Все Enterprise Edition серверов переднего плана из центрального сайта, у которых нет выровненных A / аудио-и видеоконференциями службы можно использовать одном автономного A / пула аудио-и видеоконференциями.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="f3f7b-106">Для каждого A аудио- и видео конференций, необходимо указать полное доменное имя (FQDN) для пула и является ли он будет иметь только один объект аудио- и видеоконференций или нескольких балансировку сетевой нагрузки A / V серверах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f3f7b-107">Невозможно преобразовать отдельного сервера пула в пул нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="f3f7b-108">Позднее, необходимых для организации пула нескольких серверов, необходимо удалить пул отдельного сервера и добавьте пул нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f3f7b-109">Если планируется реализовать A аудио- и видеоконференций пула в будущем, выберите **пул на нескольких компьютерах**.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f3f7b-110">Хотя пул определяется как несколько компьютеров с балансировкой нагрузки, можно создать пул из одного компьютера и присвоить этому компьютеру полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f3f7b-111">Когда вы готовы к Добавление компьютеров в пуле более поздней версии, необходимо построителя топологий еще раз, чтобы определить новый элемент пула, публикации новой топологии и затем настроить новый объект аудио- и видеоконференций пула члена с помощью Скайп для мастер развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f3f7b-112">A аудио- и видеоконференций пулы являются уникальными, в том, что они не должны подсистемы балансировки нагрузки для создания пула.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="f3f7b-113">A / пулы аудио-и видеоконференциями балансировки нагрузки во внутренней сети и не требуется дополнительное оборудование.</span><span class="sxs-lookup"><span data-stu-id="f3f7b-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

