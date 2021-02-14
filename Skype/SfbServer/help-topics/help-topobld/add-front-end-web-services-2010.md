---
title: Добавление веб-служб переднего плана 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://. Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824029"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="869e1-104">Добавление веб-служб переднего плана 2010</span><span class="sxs-lookup"><span data-stu-id="869e1-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="869e1-105">Базовый URL-адрес представляет собой удостоверение веб-служб для URL-адреса без префикса https://.</span><span class="sxs-lookup"><span data-stu-id="869e1-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="869e1-106">Например, если полный URL-адрес веб-служб пула — https://pool01.contoso.net это pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="869e1-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="869e1-107">Переопределять полное доменное имя внутреннего пула веб-служб для сервера Standard Edition невозможно.</span><span class="sxs-lookup"><span data-stu-id="869e1-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="869e1-108">При настройке балансировки нагрузки службы доменных имен (DNS) для пула переднего уровня Enterprise Edition можно указать другой внутренний базовый URL-адрес (который должен быть отличается от FQDN пула и может быть, например, внутренним). \<your base URL\></span><span class="sxs-lookup"><span data-stu-id="869e1-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="869e1-109">Можно указать внешний базовый URL-адрес, отличающийся от внутреннего базового URL-адреса, чтобы разграничить доменные имена.</span><span class="sxs-lookup"><span data-stu-id="869e1-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="869e1-110">Например, внутренним доменом является contoso.net, однако именем внешнего домена является contoso.com.</span><span class="sxs-lookup"><span data-stu-id="869e1-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="869e1-111">Внешний базовый URL-адрес следует определить с использованием имени домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="869e1-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="869e1-112">Это важно для обратных прокси-серверов, используемых в пограничном развертывании.</span><span class="sxs-lookup"><span data-stu-id="869e1-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="869e1-113">Имя домена из внешнего базового URL-адреса должно совпадать с именем домена из полного доменного имени обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="869e1-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="869e1-114">Для обмена мгновенными сообщениями и использования сведения о присутствии требуется HTTP-доступ к интерфейсному пулу.</span><span class="sxs-lookup"><span data-stu-id="869e1-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

