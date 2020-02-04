---
title: Добавление веб-служб переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698204"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="c9de0-104">Добавление веб-служб переднего плана</span><span class="sxs-lookup"><span data-stu-id="c9de0-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="c9de0-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="c9de0-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="c9de0-106">Например, если в качестве полного URL-адреса для сайтов в пуле — https://pool01.contoso.netбазовый URL-адрес — pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="c9de0-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="c9de0-107">Вы не можете переопределить полное доменное имя (FQDN) внутреннего пула веб-служб для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c9de0-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="c9de0-108">При настройке балансировки нагрузки службы доменных имен (DNS) для пула переднего плана Enterprise Edition вы можете указать другой внутренний URL-адрес, который должен отличаться от FQDN (например, внутренний URL-\<адрес\>).</span><span class="sxs-lookup"><span data-stu-id="c9de0-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="c9de0-109">Вы можете указать внешний базовый URL-адрес, который отличается от внутреннего базового URL-адреса, чтобы различать доменные имена.</span><span class="sxs-lookup"><span data-stu-id="c9de0-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="c9de0-110">Например, внутренний домен — contoso.net, но имя внешнего домена — contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c9de0-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="c9de0-111">Внешний базовый URL-адрес определяется с помощью имени домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c9de0-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="c9de0-112">Это важно для обратного прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="c9de0-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="c9de0-113">Имя домена с внешним базовым URL-адресом должно совпадать с именем домена в качестве полного доменного имени обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c9de0-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="c9de0-114">Для обмена мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP к пулу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c9de0-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

