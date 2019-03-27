---
title: Добавление полного доменного имени надежного пула приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: Чтобы определить полное доменное имя пула доверенных приложений (FQDN), укажите следующие параметры.
ms.openlocfilehash: b10053abdb8abcb11aa1a69e1acfcb97a92c4a76
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879971"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="deb39-103">Добавление полного доменного имени надежного пула приложений</span><span class="sxs-lookup"><span data-stu-id="deb39-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="deb39-104">Чтобы определить полное доменное имя пула доверенных приложений (FQDN), укажите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="deb39-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="deb39-105">Полное доменное имя сервера или пула серверов, где размещены доверенные приложения.</span><span class="sxs-lookup"><span data-stu-id="deb39-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="deb39-106">Выберите **пул на нескольких компьютерах** , если выполняется развертывание пула серверов для доверенных приложений балансировки нагрузки и обеспечения высокой доступности, или выберите **пул из одного компьютера** , если не требуется загружать Балансировка и высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="deb39-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="deb39-107">Один сервер доверенных приложений невозможно преобразовать в пуле серверов более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="deb39-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="deb39-108">Если вы думаете, что пул может потребоваться в будущем, можно развернуть несколько пула серверов, содержащий один компьютер теперь и добавьте серверы при необходимости.</span><span class="sxs-lookup"><span data-stu-id="deb39-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="deb39-109">Для получения дополнительных сведений о пулы доверенных приложений видеть [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="deb39-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

