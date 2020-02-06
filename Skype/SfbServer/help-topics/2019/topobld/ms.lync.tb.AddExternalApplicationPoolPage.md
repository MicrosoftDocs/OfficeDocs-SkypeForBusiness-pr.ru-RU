---
title: Добавление полного доменного имени надежного пула приложений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Чтобы определить полное доменное имя для пула приложений, укажите следующее:'
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787739"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="b59db-103">Добавление полного доменного имени надежного пула приложений</span><span class="sxs-lookup"><span data-stu-id="b59db-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="b59db-104">Чтобы определить полное доменное имя для пула приложений, укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="b59db-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="b59db-105">Полное доменное имя сервера или пула серверов, на которых будут размещены доверенные приложения.</span><span class="sxs-lookup"><span data-stu-id="b59db-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="b59db-106">Если вы разворачиваете пул серверов для доверенных приложений из балансировки нагрузки и высокой доступности, выберите один пул **компьютеров** , а если балансировка нагрузки или высокий уровень доступности не требуется, выберите **отдельный пул компьютеров** .</span><span class="sxs-lookup"><span data-stu-id="b59db-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b59db-107">Один сервер Trusted Applications не может быть преобразован в пул серверов позже.</span><span class="sxs-lookup"><span data-stu-id="b59db-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="b59db-108">Если вы считаете, что в будущем вам может понадобиться пул, вы можете развернуть многосерверный пул с одним компьютером сейчас и при необходимости добавить серверы.</span><span class="sxs-lookup"><span data-stu-id="b59db-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="b59db-109">Подробные сведения о пулах Trusted Applications [кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)можно найти в статьях создать.</span><span class="sxs-lookup"><span data-stu-id="b59db-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

