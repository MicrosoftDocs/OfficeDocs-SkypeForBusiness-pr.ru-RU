---
title: Добавление веб-служб переднего плана
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
ms.openlocfilehash: 20687fd74c90e6394d02ddeb2f6f37f6e4746e53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888967"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="46a3c-104">Добавление веб-служб переднего плана</span><span class="sxs-lookup"><span data-stu-id="46a3c-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="46a3c-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="46a3c-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="46a3c-106">Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="46a3c-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="46a3c-107">Не может переопределить внутренние веб-служб пула полное доменное имя (FQDN) для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="46a3c-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="46a3c-108">При настройке доменных имен (DNS) балансировку нагрузки для пула переднего плана Enterprise Edition, можно указать разные внутренний базовый URL-адрес, который должно отличаться от полного доменного ИМЕНИ пула (например, внутренний -\<базовый URL-адреса\>).</span><span class="sxs-lookup"><span data-stu-id="46a3c-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="46a3c-109">Можно указать внешний базовый URL-адрес, отличающийся от вашей внутренней базовый URL-адрес, чтобы различать доменных имен.</span><span class="sxs-lookup"><span data-stu-id="46a3c-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="46a3c-110">Например внутреннего домена — это contoso.net, но является имя внешнего домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="46a3c-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="46a3c-111">Можно определить внешний базовый URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="46a3c-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="46a3c-112">Это важно для обратных прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="46a3c-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="46a3c-113">Внешний базовый URL-адрес имя домена должно совпадать с доменное имя полное доменное имя обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="46a3c-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="46a3c-114">Обмен мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="46a3c-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

