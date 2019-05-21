---
title: Добавление полного доменного имени надежного пула приложений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Чтобы определить полное доменное имя для пула приложений, укажите следующее:'
ms.openlocfilehash: 27957348d4c6dc6b277a37d458ff21bb5efabc17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303626"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="37a46-103">Добавление полного доменного имени надежного пула приложений</span><span class="sxs-lookup"><span data-stu-id="37a46-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="37a46-104">Чтобы определить полное доменное имя для пула приложений, укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="37a46-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="37a46-105">Полное доменное имя сервера или пула серверов, на которых будут размещены доверенные приложения.</span><span class="sxs-lookup"><span data-stu-id="37a46-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="37a46-106">Если вы разворачиваете пул серверов для доверенных приложений из балансировки нагрузки и высокой доступности, выберите один пул **компьютеров** , а если балансировка нагрузки или высокий уровень доступности не требуется, выберите **отдельный пул компьютеров** .</span><span class="sxs-lookup"><span data-stu-id="37a46-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="37a46-107">Один сервер Trusted Applications не может быть преобразован в пул серверов позже.</span><span class="sxs-lookup"><span data-stu-id="37a46-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="37a46-108">Если вы считаете, что в будущем вам может понадобиться пул, вы можете развернуть многосерверный пул с одним компьютером сейчас и при необходимости добавить серверы.</span><span class="sxs-lookup"><span data-stu-id="37a46-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="37a46-109">Подробные сведения о пулах Trusted Applications [кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)можно найти в статьях создать.</span><span class="sxs-lookup"><span data-stu-id="37a46-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

