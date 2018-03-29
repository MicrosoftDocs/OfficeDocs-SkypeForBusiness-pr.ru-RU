---
title: Добавление веб-службы директора
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-web-service"></a><span data-ttu-id="c40f1-104">Добавление веб-службы директора</span><span class="sxs-lookup"><span data-stu-id="c40f1-104">Add Director Web Service</span></span>
 
<span data-ttu-id="c40f1-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="c40f1-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="c40f1-106">Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="c40f1-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="c40f1-107">Не может переопределить внутренних веб-служб пула полное доменное имя (FQDN), если выполняется развертывание только одного директора.</span><span class="sxs-lookup"><span data-stu-id="c40f1-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="c40f1-108">При настройке доменных имен (DNS) балансировку нагрузки для пула директоров, можно указать другой внутренний базовый URL-адрес (который должно отличаться от полного доменного ИМЕНИ пула и может быть, например, внутренний -\<базовый URL-адреса\>).</span><span class="sxs-lookup"><span data-stu-id="c40f1-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="c40f1-109">Можно указать внешний базовый URL-адрес, отличающийся от вашей внутренней базовый URL-адрес, чтобы различать доменных имен.</span><span class="sxs-lookup"><span data-stu-id="c40f1-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="c40f1-110">Например внутреннего домена — это contoso.net, но является имя внешнего домена contoso.com. Может определить внешний базовый URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c40f1-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="c40f1-111">Это важно для обратных прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="c40f1-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="c40f1-112">Внешний базовый URL-адрес имя домена должно совпадать с доменное имя полное доменное имя обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c40f1-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

