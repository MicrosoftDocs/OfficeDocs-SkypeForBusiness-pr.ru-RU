---
title: Добавление пула A/V MCU
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Все серверы переднего плана Enterprise Edition на центральном сайте, не поддерживающим Объединенную службу конференц-связи, могут использовать один и тот же автономный пул конференций/V. Для каждого пула конференций (/V) необходимо указать полное доменное имя (FQDN) для пула, а также будет ли он иметь только один сервер для конференц-связи A/V или несколько серверов для конференц-связи с балансировкой нагрузки.
ms.openlocfilehash: cf34ca6b82f31b0232748d15f0b0cc6597511249
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685392"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="909f9-104">Добавление пула A/V MCU</span><span class="sxs-lookup"><span data-stu-id="909f9-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="909f9-105">Все серверы переднего плана Enterprise Edition на центральном сайте, не поддерживающим Объединенную службу конференц-связи, могут использовать один и тот же автономный пул конференций/V.</span><span class="sxs-lookup"><span data-stu-id="909f9-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="909f9-106">Для каждого пула конференций (/V) необходимо указать полное доменное имя (FQDN) для пула, а также будет ли он иметь только один сервер для конференц-связи A/V или несколько серверов для конференц-связи с балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="909f9-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="909f9-107">Невозможно преобразовать односерверный пул в пул с несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="909f9-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="909f9-108">Если позже вы решите, что вашей организации требуется многосерверный пул, необходимо удалить пул с одним сервером, а затем добавить пул с несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="909f9-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="909f9-109">Если вы планируете реализовать пул конференц-связи A/V в будущем, выберите **несколько пулов компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="909f9-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="909f9-110">Хотя пул определяется как несколько компьютеров с балансировкой нагрузки, можно создать пул из одного компьютера и присвоить этому компьютеру полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="909f9-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="909f9-111">Когда вы будете готовы добавить другие компьютеры в пул позже, необходимо снова запустить Topology Builder, чтобы определить нового участника пула, опубликовать новую топологию и настроить новый участник пула конференц-связи с помощью мастера развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="909f9-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="909f9-112">Пулы серверов конференций/V являются уникальными, так как они не требуют подсистемы балансировки нагрузки для создания пула.</span><span class="sxs-lookup"><span data-stu-id="909f9-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="909f9-113">Подсистема балансировки нагрузки для пула конференц-связи с внутренними устройствами и не нуждается в дополнительном оборудовании.</span><span class="sxs-lookup"><span data-stu-id="909f9-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

