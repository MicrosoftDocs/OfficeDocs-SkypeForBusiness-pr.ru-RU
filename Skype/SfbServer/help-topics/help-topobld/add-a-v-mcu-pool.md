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
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Все серверы переднего плана Enterprise Edition центрального сайта, для которых не предусмотрена совместная служба аудио- и видеоконференций, могут использовать один и тот же отдельный пул аудио- и видеоконференций. Для каждого пула аудио- и видеоконференций необходимо указать его полное доменное имя и количество используемых серверов аудио- и видеоконференций (один сервер или несколько серверов с балансировкой нагрузки).
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217480"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="b55ed-104">Добавление пула A/V MCU</span><span class="sxs-lookup"><span data-stu-id="b55ed-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="b55ed-p102">Все серверы переднего плана Enterprise Edition центрального сайта, для которых не предусмотрена совместная служба аудио- и видеоконференций, могут использовать один и тот же отдельный пул аудио- и видеоконференций. Для каждого пула аудио- и видеоконференций необходимо указать его полное доменное имя и количество используемых серверов аудио- и видеоконференций (один сервер или несколько серверов с балансировкой нагрузки).</span><span class="sxs-lookup"><span data-stu-id="b55ed-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b55ed-p103">Пул из одного сервера нельзя преобразовать в пул из нескольких серверов. Если позднее выяснится, что для вашего предприятия требуется пул из нескольких серверов, необходимо удалить пул из одного сервера, а затем добавить пул из нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="b55ed-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="b55ed-109">Если в дальнейшем вы планируете внедрить пул аудио- и видеоконференций, выберите **Пул из нескольких компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="b55ed-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="b55ed-110">Даже если пул определен как пул с двумя или несколькими компьютерами с балансировкой нагрузки, можно создать пул с одним компьютером и указать полное доменное имя пула для одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="b55ed-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="b55ed-111">Когда вы будете готовы к добавлению дополнительных компьютеров в пул, необходимо повторно создать построитель топологий, чтобы определить новый член пула, опубликовать новую топологию, а затем настроить новый участник пула аудио-и видеоконференций с помощью мастера развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b55ed-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="b55ed-112">Пулы сервера аудио- и видеоконференций являются уникальными, поэтому балансировка нагрузки при создании пула не требуется.</span><span class="sxs-lookup"><span data-stu-id="b55ed-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="b55ed-113">Пулы аудио- и видеоконференций выполняют внутреннюю балансировку нагрузки и не требуют привлечения дополнительного оборудования.</span><span class="sxs-lookup"><span data-stu-id="b55ed-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

