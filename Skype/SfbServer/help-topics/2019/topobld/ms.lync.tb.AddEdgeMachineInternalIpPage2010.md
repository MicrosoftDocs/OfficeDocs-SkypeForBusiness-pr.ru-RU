---
title: Добавление пограничного сервера внутренний IP-адреса сервера 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полное доменное имя (FQDN) для пограничного сервера.
ms.openlocfilehash: d25819b45fea7ba46501e931beeb8d5032b43c1f
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975387"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="899c8-103">Добавление пограничного сервера внутренний IP-адреса сервера 2010</span><span class="sxs-lookup"><span data-stu-id="899c8-103">Add Edge Machine Internal IP 2010</span></span>
 
<span data-ttu-id="899c8-104">Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полное доменное имя (FQDN) для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="899c8-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>
  
- <span data-ttu-id="899c8-105">В поле **Внутренний адрес IPv4**введите IP-адрес пограничного сервера, который нужно добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="899c8-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>
    
- <span data-ttu-id="899c8-106">В поле **Внутреннее полное доменное имя**введите полное доменное имя (FQDN) пограничного сервера, который нужно добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="899c8-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>
    
<span data-ttu-id="899c8-107">Полное доменное имя, которое указывается должен быть идентичен имя компьютера, который настроен на сервере.</span><span class="sxs-lookup"><span data-stu-id="899c8-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="899c8-108">По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="899c8-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="899c8-109">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="899c8-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="899c8-110">Таким образом необходимо настроить суффикс доменных имен (DNS) на имя компьютера, развертываемом в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="899c8-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="899c8-111">Сведения о добавлении DNS-суффикса к имени компьютера в разделе [Настройка DNS для поддержки пограничной топологии](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="899c8-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>
  

