---
title: Добавление веб-служб переднего плана 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
ms.openlocfilehash: 5d5c935d1357c2baf66ed17ab762db8fd442ac67
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976895"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="0e606-104">Добавление веб-служб переднего плана 2010</span><span class="sxs-lookup"><span data-stu-id="0e606-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="0e606-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="0e606-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="0e606-106">Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="0e606-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="0e606-107">Не может переопределить внутренние веб-служб пула полное доменное имя (FQDN) для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0e606-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="0e606-108">При настройке доменных имен (DNS) балансировку нагрузки для пула переднего плана Enterprise Edition, можно указать другой внутренний базовый URL-адрес (который должно отличаться от полного доменного ИМЕНИ пула и может быть, например, внутренний -\<базовый URL-адреса\>).</span><span class="sxs-lookup"><span data-stu-id="0e606-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="0e606-109">Можно указать внешний базовый URL-адрес, отличающийся от вашей внутренней базовый URL-адрес, чтобы различать доменных имен.</span><span class="sxs-lookup"><span data-stu-id="0e606-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="0e606-110">Например внутреннего домена — это contoso.net, но является имя внешнего домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0e606-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="0e606-111">Может определить внешний базовый URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0e606-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="0e606-112">Это важно для обратных прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0e606-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="0e606-113">Внешний базовый URL-адрес имя домена должно совпадать с доменное имя полное доменное имя обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="0e606-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="0e606-114">Обмен мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0e606-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

