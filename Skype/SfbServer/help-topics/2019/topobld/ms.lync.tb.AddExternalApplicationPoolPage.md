---
title: Добавление полного доменного имени надежного пула приложений
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы определить полное доменное имя пула доверенных приложений, укажите следующие параметры.
ms.openlocfilehash: e34c3ba68a90e292da9441465d9077112b1ce173
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811819"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="7947f-103">Добавление полного доменного имени пула доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="7947f-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="7947f-104">Чтобы определить полное доменное имя пула доверенных приложений, укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="7947f-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="7947f-105">Полное доменное имя сервера или пула серверов, где размещены доверенные приложения.</span><span class="sxs-lookup"><span data-stu-id="7947f-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="7947f-106">Выберите параметр **Пул с несколькими компьютерами** при развертывании пула серверов для доверенных приложений с поддержкой балансировки нагрузки и высокой доступности или выберите **Отдельный пул компьютеров**, если нет необходимости в балансировки нагрузки или высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="7947f-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7947f-p101">Отдельный сервер доверенных приложений не может быть преобразован в пул серверов. Если в будущем может понадобиться пул, можно развернуть на данном этапе пул серверов, состоящий только из одного сервера, а впоследствии добавить в него серверы.</span><span class="sxs-lookup"><span data-stu-id="7947f-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="7947f-109">Дополнительные сведения о пуле доверенных приложений см. в разделе [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7947f-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

