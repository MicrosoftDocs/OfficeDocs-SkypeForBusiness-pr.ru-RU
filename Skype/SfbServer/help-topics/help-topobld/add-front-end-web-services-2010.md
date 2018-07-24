---
title: Добавление веб-служб переднего плана 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.
ms.openlocfilehash: 1e18c4956e9b9d369bae766ed557debe44586298
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015706"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="9df92-104">Добавление веб-служб переднего плана 2010</span><span class="sxs-lookup"><span data-stu-id="9df92-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="9df92-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="9df92-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="9df92-106">Например, если — это полный URL-адрес для веб-служб пула https://pool01.contoso.net, базовый URL-адрес является pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="9df92-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="9df92-107">Не может переопределить внутренние веб-служб пула полное доменное имя (FQDN) для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9df92-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="9df92-108">При настройке доменных имен (DNS) балансировку нагрузки для пула переднего плана Enterprise Edition, можно указать другой внутренний базовый URL-адрес (который должно отличаться от полного доменного ИМЕНИ пула и может быть, например, внутренний -\<базовый URL-адреса\>).</span><span class="sxs-lookup"><span data-stu-id="9df92-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="9df92-109">Можно указать внешний базовый URL-адрес, отличающийся от вашей внутренней базовый URL-адрес, чтобы различать доменных имен.</span><span class="sxs-lookup"><span data-stu-id="9df92-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="9df92-110">Например внутреннего домена — это contoso.net, но является имя внешнего домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9df92-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="9df92-111">Может определить внешний базовый URL-адрес, используя имя домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9df92-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="9df92-112">Это важно для обратных прокси-серверов для развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="9df92-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="9df92-113">Внешний базовый URL-адрес имя домена должно совпадать с доменное имя полное доменное имя обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="9df92-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="9df92-114">Обмен мгновенными сообщениями и присутствия требуется доступ по протоколу HTTP для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9df92-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

